# RULES.md — hard pre-trade gates

Every order Bull proposes must pass **every** rule below. If any rule fails, the order is rejected. Log rejections in `memory/research_log.md` so we can review them.

These rules are **non-negotiable** at runtime. They are tunable between sessions by the user — but a routine never bypasses them mid-session.

---

## Position sizing

| # | Rule | Verification |
|---|---|---|
| P1 | **Max 5% of portfolio equity** in any single new position at entry. | `intended_dollars / current_equity <= 0.05` |
| P2 | **Max 15% of portfolio equity** in any single ticker (incl. existing position). | After-fill exposure check before placing. |
| P3 | **Risk per trade ≤ 1.5% of equity.** Risk = `(entry − stop) / entry × position_size`. | Compute before placing. Reject if over. |
| P4 | **R/R ≥ 2:1** required. Take-profit target distance ≥ 2× stop-loss distance. | Compute from entry, stop, target. |

## Concurrency

| # | Rule | Verification |
|---|---|---|
| C1 | **Max 3 new positions per calendar week.** | Count entries in `trade_log.md` since Monday. |
| C2 | **Max 8 open positions at any time.** | Count positions in `portfolio.md`. |
| C3 | **No averaging down.** Never add to a losing position. | If ticker has unrealized P&L < 0, reject any new BUY on it. |

## Stop & exit discipline

| # | Rule | Verification |
|---|---|---|
| S1 | **Every entry sets a 10% trailing stop** at fill. | Place bracket order with `trail_percent=10` on the SELL leg. |
| S2 | **Cut −7% losers at midday.** Any open position with unrealized P&L ≤ −7% from entry is closed at next midday routine. | Midday routine enforces. |
| S3 | **Tighten stops on winners ≥ +15%.** Move trailing from 10% → 7%. | Midday routine. |
| S4 | **No stop-loss = no position.** If trailing stop fails to set on Alpaca, immediately close the position. | Verify after place. |

## Asset / instrument scope

| # | Rule | Verification |
|---|---|---|
| A1 | **US stocks and ETFs only.** | Reject anything that's not equity/ETF. |
| A2 | **No options. Ever.** | No `option_*` symbols. |
| A3 | **No crypto.** | No `*USD` crypto pairs. |
| A4 | **No leverage / margin.** Cash account only. | `Account.buying_power == Account.cash` check. |
| A5 | **Min average daily volume 1M shares.** Avoid illiquid names. | Verify via Alpaca asset metadata or research. |
| A6 | **Min price $5.** No penny stocks. | `last_price >= 5.0` |

## Day & loss controls

| # | Rule | Verification |
|---|---|---|
| D1 | **Daily loss cap −2% of equity.** When breached, set `halt_today: YES` in `portfolio.md` and skip all entries until next day. | EOD checks; midday/open also checks. |
| D2 | **No new entries after 15:30 ET.** Last 30 min are noisy. | Open routine fires at 09:35; if it ever runs late, this is a backstop. |
| D3 | **Trading-day blackout: FOMC days, CPI release days, NFP first-Friday.** No new entries. Position management still allowed. | Premarket routine checks an inline calendar list. |
| D4 | **Weekly loss cap −5% of equity from prior Friday close.** When breached, posture defensive: no new entries for the rest of the week. | EOD checks after each daily P&L. |
| D5 | **Drawdown kill-switch −10% from peak equity.** Liquidate all positions, set `halt_until_human: YES`, open a GH issue tagged `kill-switch`. Halt routines until user re-arms. | Any routine that reads portfolio checks this. |

## Operational

| # | Rule | Verification |
|---|---|---|
| O1 | **API keys read from env vars only.** Never echoed in logs, commits, or issues. | Code review of routine prompts. |
| O2 | **Every routine commits and pushes its memory updates** before exiting. | `git status` clean at end. |
| O3 | **Order placement is idempotent.** Use a `client_order_id` keyed on date + ticker so re-runs don't double-buy. | Format: `bull-YYYYMMDD-<TICKER>-<routine>` |
| O4 | **Confirm fills.** After placing an order, poll Alpaca until status is `filled` or 60s elapses. Log either way. | |
| O5 | **Paper / live mismatch protection.** If `ALPACA_BASE_URL` doesn't match the env name (`paper-api` ↔ paper account; bare `api` ↔ live), abort. | Sanity check at boot. |

---

## When rules conflict

If a position would violate a rule that wasn't violated at entry (e.g. P2 — concentration grew because the ticker rallied), the rule applies *to new orders*, not as a forced unwind. Don't sell to fix concentration unless trailing stop or another rule triggers a sell on its own.

The kill-switch (D5) overrides everything.
