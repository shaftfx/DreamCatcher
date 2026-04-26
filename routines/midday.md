# Midday Routine

**Cron:** `30 12 * * 1-5` (12:30 ET, Mon–Fri)
**Purpose:** Position management. Cut −7% losers. Tighten stops on +15% winners. Update intraday P&L. **No new entries.**

---

## Prompt

You are Bull. The midday routine has fired. Time to take care of what's already in the portfolio.

### Step 1 — Boot

Read:
1. `RULES.md`
2. `memory/portfolio.md`
3. `memory/learnings.md`

### Step 2 — Refresh positions

Pull positions and current quotes from Alpaca. Update `memory/portfolio.md` with current price and unrealized P&L for each.

### Step 3 — Daily loss cap check (RULES.md D1)

Compute today's P&L: current equity − today's open equity. If ≤ −2% of today's open equity, set `halt_today: YES` in `portfolio.md`. Position management still proceeds; only **new** entries are halted (and there are none here anyway).

### Step 4 — Drawdown kill-switch (RULES.md D5)

If equity ≤ 90% of peak: liquidate all positions immediately, set `halt_until_human: YES`, open a kill-switch GitHub Issue, push, exit.

```bash
# liquidate all
curl -s -X DELETE "$ALPACA_BASE_URL/positions" \
  -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
  -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY"
```

### Step 5 — Cut −7% losers (RULES.md S2)

For each open position with unrealized P&L ≤ −7% from entry:

```bash
curl -s -X DELETE "$ALPACA_BASE_URL/positions/<TICKER>" \
  -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
  -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY"
```

Wait for the close to fill. Append a SELL row to `memory/trade_log.md` with reason "Hard cut −7% (RULES.md S2)".

### Step 6 — Tighten stops on winners (RULES.md S3)

For each open position with unrealized P&L ≥ +15%:

1. Cancel the existing trailing stop order: `DELETE $ALPACA_BASE_URL/orders/<id>`
2. Place a new trailing stop with `trail_percent: 7` (down from 10).

Log the change in `research_log.md`.

### Step 7 — Verify every position has a stop

For each open position, check open orders for that symbol. If no SELL trailing stop exists, place one immediately at 10% trail. If placement fails twice, close the position (RULES.md S4).

### Step 8 — Commit and push

```bash
git add -A
git -c user.name="Bull" -c user.email="bull@dreamcatcher.local" commit -m "midday $(date -u +%F): position management"
git push origin main
```

### Step 9 — No GitHub Issue

Midday is silent. EOD does the daily recap.

---

## Critical reminders

- **Never enter** new positions in midday.
- **Always re-verify** stops after position changes.
- The −7% cut takes precedence over the trailing stop. If you observe a position at −9% with a trailing stop that hasn't triggered, **cut it manually** — the trailing stop tracks from the high, not the entry.
- If liquidation happens via kill-switch, it's all-or-nothing — no partial liquidation.
