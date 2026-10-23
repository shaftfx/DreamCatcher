# Skill: research-stock

Used by `routines/premarket.md` (and occasionally other routines that need to re-validate a thesis).

**Input:** a ticker symbol and the reason for researching it (e.g. "earnings catalyst," "follow-up on prior watch," "downgrade reaction").

**Output:** a structured research entry appended to `memory/research_log.md` with a clear `decision: queued | passed | rejected`.

---

## Procedure

### 1. Confirm the instrument is tradeable

```bash
curl -s -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
        -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
  "$ALPACA_BASE_URL/assets/<TICKER>"
```

Verify: `tradable=true`, `class=us_equity` or `us_etf`, `status=active`. If any of these fail, decision = `rejected (untradeable)`.

### 2. Pull current quote and recent bars

Use Alpaca's **data** endpoint (different from trading):

```bash
DATA_URL="https://data.alpaca.markets/v2"

# Latest quote
curl -s -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
        -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
  "$DATA_URL/stocks/<TICKER>/quotes/latest"

# 60 days of daily bars (for SMA, RSI, volume avg)
curl -s -H "APCA-API-KEY-ID: $ALPACA_API_KEY" \
        -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
  "$DATA_URL/stocks/<TICKER>/bars?timeframe=1Day&limit=60"
```

Parse out:
- `current_price` (latest ask/bid midpoint)
- `last_close` (yesterday's close)
- `sma_50` = mean of last 50 daily closes
- `volume_20_avg` = mean of last 20 daily volumes
- `today_volume` = today's bar so far (or yesterday if pre-market)
- `rsi_14` = computed from 14-day Wilder's smoothing of gains/losses (formula in `KNOWLEDGE/indicators.md`)
- `recent_candle_pattern` = a one-line read of yesterday's daily candle (hammer / engulfing / doji / normal — see `KNOWLEDGE/candlestick_patterns.md`)

### 3. Web research — thesis + catalyst

Use WebSearch to gather: bull case, upcoming catalyst, top risks, recent EPS/revenue/guidance.

Run these searches in sequence:

1. `<TICKER> bull case catalyst next 60 days site:seekingalpha.com OR site:fool.com OR site:investors.com`
2. `<TICKER> earnings date next quarter 2026`
3. `<TICKER> recent earnings EPS revenue guidance beat miss`
4. `<TICKER> analyst upgrade downgrade 2026`

Then WebFetch the company's IR page (`<TICKER> investor relations`) for the most recent earnings release if the searches return thin results.

Synthesize into a 2-3 sentence thesis covering: fundamental health, upcoming catalyst with date, top risk. Note all sources used.

### 4. Apply the three-leg entry framework (`STRATEGY.md`)

Score each leg explicitly:

| Leg | Pass criteria | Status |
|---|---|---|
| **Fundamental** | Beat last 2 ER + raised guidance, OR sector tailwind, OR reasonable valuation cited in research | ✅ / ❌ |
| **Catalyst** | Specific event with a date within the next 8 weeks | ✅ / ❌ |
| **Technical** | Price > sma_50 AND rsi_14 ∈ [40, 70] AND today_volume ≥ 1.5 × volume_20_avg AND no bearish recent candle pattern | ✅ / ❌ |

**Decision rule:** queue if at least 2 of 3 legs pass. If only fundamental + technical (no catalyst), flag `half_size: true` for the open routine.

### 5. Apply pre-screen rule gates (`RULES.md`)

Even before the open routine validates, sanity-check:

- A1: `class` is `us_equity` or `us_etf` ✓
- A5: `volume_20_avg` ≥ 1,000,000 ✓
- A6: `current_price` ≥ $5 ✓
- A2/A3: ticker doesn't end in `USD` (crypto pair), no option symbol prefix ✓

If any pre-screen fails: decision = `rejected (rule fail)`.

### 6. Compute a draft entry plan (only if queued)

```
entry_price = current_price
stop_price  = max(
  recent_swing_low_20d,    # lowest low of last 20 daily bars
  entry_price * 0.92       # 8% hard floor
)
risk_per_share = entry_price - stop_price
target_price   = entry_price + 2 * risk_per_share          # R/R = 2:1 minimum
risk_dollars   = 0.01 * current_equity                     # 1% default
shares         = floor(risk_dollars / risk_per_share)
position_value = shares * entry_price
```

Sanity check: `position_value <= 0.05 * current_equity`. If not, scale `shares` down so it fits, recompute `risk_dollars`.

### 7. Append to `memory/research_log.md`

Use this exact format (newest first; insert at the top of the "Research Entries" section):

```markdown
### YYYY-MM-DD HH:MM UTC — premarket — TICKER

**Thesis:** <2–3 sentences synthesized from web research.>

**Catalyst:** <event> on <date>

**Fundamentals:**
- Last EPS: $X.XX vs est $X.XX (beat/miss/in-line)
- Revenue YoY: ±X.X%
- Guidance: raised / maintained / cut
- Valuation: P/E XX, P/S X.X (sector median XX)

**Technicals:**
- Price: $X.XX (SMA50: $X.XX, +X.X% above)
- RSI(14): XX
- Volume: today X.XM vs 20d avg X.XM (+X.X×)
- Recent candle: <pattern>

**Entry framework legs (need ≥ 2 of 3):**
- Fundamental: ✅ / ❌ — <one-line reason>
- Catalyst: ✅ / ❌ — <one-line reason>
- Technical: ✅ / ❌ — <one-line reason>

**Draft plan (if queued):**
- Entry: $X.XX
- Stop: $X.XX (-X.X%)
- Target: $X.XX (+X.X%, R/R 2:1)
- Risk: $XX.XX (X.X% of equity)
- Shares: XX (position $X,XXX, X.X% of equity)
- Half-size flag: yes/no

**Sources:**
- <url 1>
- <url 2>

**Decision:** queued | passed | rejected (<reason>)
```

### 8. Update `memory/research_log.md`'s Active Watchlist

If decision is `queued`: ensure the ticker is in the Active Watchlist table at the top. If it was `rejected` and was previously queued, remove it.

---

## Failure modes & fallbacks

- **WebSearch returns thin results:** WebFetch the company's IR page directly + a financial news source (Reuters, Bloomberg, CNBC). Note source quality in the entry.
- **Alpaca returns 403 / 401:** auth failure. Abort the routine, log to `research_log.md` with `error: auth_failure`, push, exit. Do not invent fake data.
- **Bars endpoint returns < 50 bars:** the ticker is too new (recent IPO). Decision = `rejected (insufficient history)`.
- **All three legs fail:** decision = `passed` (not rejected — the name might earn its way back later). Don't add to active watchlist.
