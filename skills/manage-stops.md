# Skill: manage-stops

Used by `routines/midday.md` to evaluate every open position and act on it.

**Input:** the current positions list from Alpaca.
**Output:** for each position — one of `cut`, `tighten`, `verify_stop`, `leave`. Plus the trade_log/portfolio updates.

---

## Procedure (per position)

### 1. Pull fresh data

```bash
POSITIONS=$(curl -s -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
                    -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
            "$ALPACA_BASE_URL/positions")
```

Parse each row:
- `symbol`, `qty`, `avg_entry_price`, `current_price`, `unrealized_pl`, `unrealized_plpc` (decimal, e.g. -0.045 = -4.5%)

### 2. Decide the action — order matters

**Check 1: hard cut at −7% (RULES.md S2)**

If `unrealized_plpc <= -0.07`: action = `cut`.

**Check 2: tighten stop on +15% winner (RULES.md S3)**

Else if `unrealized_plpc >= 0.15`: action = `tighten`.

**Check 3: stop attached?**

Else: list open orders for the symbol. If no SELL trailing_stop in `{accepted, new, held}` exists: action = `verify_stop` (re-attach a 10% trailing stop, or close the position if attach fails twice — same logic as `place-trade.md` Step 7).

**Else:** action = `leave`. Don't touch.

---

## Action: cut

```bash
curl -s -X DELETE "$ALPACA_BASE_URL/positions/<TICKER>?percentage=100" \
  -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
  -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY"
```

This sends a market sell for the full position. Wait for fill (poll like `place-trade.md` Step 5).

Append to `trade_log.md`:

```markdown
| <ISO UTC> | midday | SELL | <TICKER> | <qty> | <fill_price> | — | — | — | <realized_pnl> | Hard cut −7% (RULES.md S2) |
```

Update `portfolio.md`: remove position. The trailing stop on Alpaca should auto-cancel when the position goes to zero — verify by listing open orders for the ticker; cancel any leftovers manually:

```bash
curl -s -X DELETE "$ALPACA_BASE_URL/orders/<order_id>" \
  -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
  -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY"
```

---

## Action: tighten

1. List open orders for the ticker. Find the existing SELL trailing_stop, capture its `id`.
2. Cancel it:

```bash
curl -s -X DELETE "$ALPACA_BASE_URL/orders/<old_trail_id>" \
  -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
  -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY"
```

3. Place a new trailing stop at 7%:

```bash
TODAY=$(date -u +%Y%m%d)
NEW_TRAIL_ID="bull-${TODAY}-<TICKER>-trail7"

curl -s -X POST "$ALPACA_BASE_URL/orders" \
  -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
  -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
  -H "Content-Type: application/json" \
  -d "{
    \"symbol\": \"<TICKER>\",
    \"qty\": \"<qty>\",
    \"side\": \"sell\",
    \"type\": \"trailing_stop\",
    \"trail_percent\": \"7\",
    \"time_in_force\": \"gtc\",
    \"client_order_id\": \"${NEW_TRAIL_ID}\"
  }"
```

4. Verify (Step 7 of `place-trade.md`). If new stop fails to attach within retries, **DO NOT** close the position from this action — instead, re-place a 10% trail and log a warning. (Tightening is an upgrade, not a survival action; preserving the existing trailing stop should be the priority — but we already cancelled it. This is a known race; mitigate by placing the new stop FIRST then cancelling the old, but Alpaca won't allow two opposing SELLs of the same qty. So: cancel-then-place is the order, and we accept the brief gap. If it fails, default back to a 10% trail at all costs.)

5. Append a note to `research_log.md`: "tightened <TICKER> stop 10% → 7% at +X.X%".

---

## Action: verify_stop

Re-attach a 10% trailing stop. Same as `place-trade.md` Steps 6–7. If it fails after retry, close the position (RULES.md S4). Log either way.

This branch fires when something has gone wrong — usually a partial fill at entry, or Alpaca cancelled the stop unexpectedly. Worth a learnings.md note if it happens more than once.

---

## Action: leave

Update `portfolio.md` with current price and unrealized P&L. Done.

---

## After all positions handled

- Save the updated `portfolio.md`.
- If any position was cut for −7%, consider whether the daily loss cap (D1) is now in danger — recompute today's P&L and set `halt_today: YES` if breached.
- Commit, push.
