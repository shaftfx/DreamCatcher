# Skill: place-trade

Used by `routines/open.md` to execute one queued entry.

**Input:** a research-log entry with `decision: queued` and a complete draft plan (entry, stop, target, shares, risk).

**Output:** either a filled position with an attached trailing stop (and a row in `trade_log.md`), or a rejected entry with reason logged.

---

## Pre-flight: market is open?

```bash
CLOCK=$(curl -s -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
                -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
        "$ALPACA_BASE_URL/clock")
```

If `is_open=false`, abort the trade. Log to `research_log.md`: `skipped (market_closed)`. The user may have scheduled a Run Now on a holiday — don't trade.

---

## Procedure

### 1. Don't chase

```bash
QUOTE=$(curl -s -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
                -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
        "https://data.alpaca.markets/v2/stocks/<TICKER>/quotes/latest")
```

Compare `current_price` vs the planned entry from research. If `current_price > planned_entry × 1.015` (price gapped >1.5% above plan), abort. The premise of the entry was that price was at a specific level — if it's already much higher, the R/R math is broken.

Log `skipped (chased: planned $X, now $Y)`.

### 2. Re-validate every rule (do not trust prior validation)

Re-check each rule from `RULES.md`:

- P1, P2, P3, P4 (sizing + R/R)
- C1: count entries in `trade_log.md` since this Monday — must be < 3
- C2: count current positions — must be < 8
- C3: ticker not currently held with negative unrealized P&L
- A1, A2, A3, A4, A5, A6
- D1: `halt_today: NO`
- D2: time is before 15:30 ET (open routine fires at 09:35 — should always pass, but check)
- D3: today is not a blackout day
- D4: `weekly_defensive: NO`
- D5: equity > 0.9 × peak

If any rule fails: decision = `rejected (rule X)`. Skip the trade. Log.

### 3. Recompute sizing against current equity

The premarket plan used yesterday's equity. Refresh:

```bash
ACCOUNT=$(curl -s -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
                  -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
          "$ALPACA_BASE_URL/account")
```

Parse `equity` and recompute:

```
risk_dollars   = 0.01 × equity        (or 0.005 × equity for ETFs)
risk_per_share = current_price − stop_price
shares         = floor(risk_dollars / risk_per_share)
position_value = shares × current_price
```

If `position_value > 0.05 × equity`: scale `shares` down to fit. Re-check `shares > 0`; if zero, decision = `rejected (sizing degenerate)`.

If the queued entry was flagged `half_size: true`: use `0.005 × equity` instead of `0.01`.

### 4. Place market BUY with idempotent client_order_id

```bash
TODAY=$(date -u +%Y%m%d)
ORDER_ID="bull-${TODAY}-<TICKER>-open"

BUY_RESP=$(curl -s -X POST "$ALPACA_BASE_URL/orders" \
  -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
  -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
  -H "Content-Type: application/json" \
  -d "{
    \"symbol\": \"<TICKER>\",
    \"qty\": \"<SHARES>\",
    \"side\": \"buy\",
    \"type\": \"market\",
    \"time_in_force\": \"day\",
    \"client_order_id\": \"${ORDER_ID}\",
    \"extended_hours\": false
  }")
```

Capture `order_id` (Alpaca's UUID) from the response.

If response is 422 with "client_order_id already exists" — that means a prior run already placed this order. Look up existing order by `client_order_id`:

```bash
curl -s -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
        -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
  "$ALPACA_BASE_URL/orders?client_order_id=${ORDER_ID}"
```

Resume from Step 5 with that order's status.

### 5. Poll for fill (max 60 s)

```bash
for i in $(seq 1 12); do
  ORDER=$(curl -s -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
                  -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
          "$ALPACA_BASE_URL/orders/<ORDER_UUID>")
  STATUS=$(echo "$ORDER" | jq -r '.status')
  if [ "$STATUS" = "filled" ]; then break; fi
  if [ "$STATUS" = "rejected" ] || [ "$STATUS" = "canceled" ]; then break; fi
  sleep 5
done
```

If `status != filled` after the loop:
- `partial_fill`: accept partial, log the actual `filled_qty` and proceed to attach a trailing stop sized to `filled_qty`
- `rejected`: log reason, decision = `rejected (broker: <reason>)`, exit
- `pending` after 60s: cancel the order, log `timeout`, exit

Pull `filled_avg_price` and `filled_qty` from the filled order.

### 6. Attach trailing stop SELL

```bash
TRAIL_ID="bull-${TODAY}-<TICKER>-trail"

curl -s -X POST "$ALPACA_BASE_URL/orders" \
  -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
  -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
  -H "Content-Type: application/json" \
  -d "{
    \"symbol\": \"<TICKER>\",
    \"qty\": \"<FILLED_QTY>\",
    \"side\": \"sell\",
    \"type\": \"trailing_stop\",
    \"trail_percent\": \"10\",
    \"time_in_force\": \"gtc\",
    \"client_order_id\": \"${TRAIL_ID}\"
  }"
```

### 7. Verify the stop attached

Wait 5s, then list open orders for the ticker:

```bash
curl -s -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
        -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
  "$ALPACA_BASE_URL/orders?status=open&symbols=<TICKER>"
```

Confirm there's at least one SELL trailing_stop with status in {`accepted`, `new`, `held`}. If not, retry placement once. If second attempt fails:

```bash
# RULES.md S4: no stop = no position
curl -s -X DELETE "$ALPACA_BASE_URL/positions/<TICKER>?qty=<FILLED_QTY>" \
  -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
  -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY"
```

Log: `closed (stop_attach_failed)`.

### 8. Append to trade_log.md

```markdown
| <ISO UTC timestamp> | open | BUY | <TICKER> | <FILLED_QTY> | <FILLED_AVG_PRICE> | trail 10% | $<TARGET> | $<RISK_DOLLARS> | — | <one-line thesis from research_log.md> |
```

### 9. Update portfolio.md

Add the new position to the open positions table. Increment "new entries this week" count. Note the trailing-stop level.

### 10. Mark the research entry as executed

In `memory/research_log.md`, change the entry's `Decision: queued` to `Decision: executed (filled at $X.XX)`.

---

## Critical guardrails

- **One open SELL trailing stop per position. Always.** If you find a position without a stop at any check, immediately place one or close.
- **Idempotency.** `client_order_id` ensures re-running doesn't double-buy.
- **No staged orders.** Don't place a stop before the BUY fills — Alpaca will reject sells with no position.
- **Don't echo API keys.** Even when logging an error response, redact headers.
