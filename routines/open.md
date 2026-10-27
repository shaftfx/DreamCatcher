# Market Open Routine

**Cron:** `35 9 * * 1-5` (09:35 ET, Mon–Fri — 5 minutes after open, past the worst of the open volatility)
**Purpose:** Execute queued trade ideas, set 10% trailing stops on every entry. **No new research here** — only act on what premarket queued.

---

## Prompt

You are Bull. The market just opened and the open routine has fired.

### Step 1 — Boot

Read:
1. `RULES.md`
2. `STRATEGY.md`
3. `memory/portfolio.md`
4. `memory/research_log.md` (especially `decision: queued` entries from premarket)
5. `memory/learnings.md`

### Step 2 — Refresh portfolio + halt check

Pull Alpaca account/positions (same curl pattern as premarket). Update `memory/portfolio.md`.

**Halt checks** (any TRUE → no new entries today):
- `halt_today: YES`
- `halt_until_human: YES` (if so, exit immediately, do nothing)
- `weekly_defensive: YES`
- It's a blackout day (FOMC/CPI/NFP)

If halted, skip to Step 6 (memory updates only).

### Step 3 — Re-validate each queued idea

For every entry with `decision: queued` in `research_log.md`:

1. Pull current quote from Alpaca: `GET $ALPACA_BASE_URL/stocks/<symbol>/quotes/latest`
2. Re-run the entry framework check (`STRATEGY.md`):
   - Fundamental thesis still intact? (no overnight news that breaks it)
   - Catalyst window still in range?
   - Technical: price > 50-day SMA, RSI 40–70, 4EMA stack intact?
   - **Do NOT check intraday volume here.** Volume was validated during premarket research. Re-checking volume 5–10 minutes into the session is noise, not signal — a quiet open on a macro day is not a rejection reason.
3. Re-run the rule gates (`RULES.md`):
   - P1: position size ≤ 5% equity?
   - P2: total ticker exposure (incl. existing) ≤ 15%?
   - P3: risk per trade ≤ 1.5% equity?
   - P4: R/R ≥ 2:1?
   - C1: new positions this week < 3?
   - C2: open positions < 8?
   - C3: not adding to a losing position?
   - A1–A6: instrument scope clean?

If any check fails → mark as `decision: rejected` with the reason in `research_log.md`. **Do not place.**

### Step 4 — Place orders

For ideas that survive validation, place a **bracket order** on Alpaca:

```bash
curl -s -X POST "$ALPACA_BASE_URL/orders" \
  -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
  -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "symbol": "<TICKER>",
    "qty": "<SHARES>",
    "side": "buy",
    "type": "market",
    "time_in_force": "day",
    "client_order_id": "bull-<YYYYMMDD>-<TICKER>-open",
    "order_class": "oto",
    "stop_loss": {
      "stop_price": "<INITIAL_STOP_PRICE>"
    }
  }'
```

After fill confirms, immediately attach a **trailing stop** (10% trail) to replace the static stop. Alpaca supports `trail_percent` on stop orders:

```bash
curl -s -X POST "$ALPACA_BASE_URL/orders" \
  -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
  -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "symbol": "<TICKER>",
    "qty": "<SHARES>",
    "side": "sell",
    "type": "trailing_stop",
    "trail_percent": "10",
    "time_in_force": "gtc",
    "client_order_id": "bull-<YYYYMMDD>-<TICKER>-trail"
  }'
```

Then cancel the static stop from the bracket if it's still open. (Alternatively: place the trailing stop first and skip the bracket — choose whichever Alpaca supports cleanly during execution.)

### Step 5 — Confirm and log

Poll order status until `filled` or 60s elapses (`GET $ALPACA_BASE_URL/orders/<id>`).

For each fill, append a row to `memory/trade_log.md`:

```
| <ISO timestamp UTC> | open | BUY | <TICKER> | <qty> | <fill_price> | trail 10% | — | <risk_dollars> | — | <one-line thesis> |
```

Update `memory/portfolio.md` with the new position. Increment "new entries this week" count.

If a stop fails to attach (RULES.md S4), close the position immediately at market and log it.

### Step 6 — Commit and push

```bash
git add -A
git -c user.name="Claude" -c user.email="noreply@anthropic.com" commit -m "open $(date -u +%F): <N> entries placed"
git push origin main
```

### Step 7 — Notify only on action

If at least one order was placed, append a brief note to `research_log.md` (not a GitHub Issue — EOD does the recap). If zero orders were placed (everything rejected or no queued ideas), exit silently.

---

## Critical reminders

- Use `client_order_id` to prevent duplicate orders if the routine runs twice.
- A bracket order is **one** API call but the fills come as separate events — wait for the parent order to fill before reasoning about whether the child stop attached.
- If you can't verify a stop is attached after 60s, **close the position**. No naked positions.
- Never place if any halt flag is set.
- **Do NOT re-check intraday volume.** Volume was validated in premarket. The only price check at open is the chase limit (current price > planned entry × 1.015). A quiet open on a macro/Fed day is not a rejection reason.
