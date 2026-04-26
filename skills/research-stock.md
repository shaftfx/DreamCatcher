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

### 3. Run Perplexity research — thesis + catalyst

```bash
RESEARCH=$(curl -s https://api.perplexity.ai/chat/completions \
  -H "Authorization: Bearer $PERPLEXITY_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "sonar-reasoning-pro",
    "messages": [
      {"role":"system","content":"You are a financial research analyst. Be precise, cite sources, prefer SEC filings and primary sources."},
      {"role":"user","content":"For ticker <TICKER>: (1) what is the current bull case over the next 4-8 weeks, (2) what specific upcoming catalyst supports it (earnings, product, regulatory, macro), (3) what are the top 2 risks, (4) what is the most recent EPS, revenue, and guidance commentary? Cite sources."}
    ],
    "temperature": 0.2
  }')
```

Save the full response (with citations) for inclusion in the research log entry.

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

**Thesis:** <2–3 sentences synthesized from Perplexity research.>

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
- <perplexity citation 1>
- <perplexity citation 2>

**Decision:** queued | passed | rejected (<reason>)
```

### 8. Update `memory/research_log.md`'s Active Watchlist

If decision is `queued`: ensure the ticker is in the Active Watchlist table at the top. If it was `rejected` and was previously queued, remove it.

---

## Failure modes & fallbacks

- **Perplexity 429 (rate limit):** retry once after 30s. If still failing, fall back to WebSearch + WebFetch on the company's IR page and a financial news source. Note the fallback in the entry.
- **Alpaca returns 403 / 401:** auth failure. Abort the routine, log to `research_log.md` with `error: auth_failure`, push, exit. Do not invent fake data.
- **Bars endpoint returns < 50 bars:** the ticker is too new (recent IPO). Decision = `rejected (insufficient history)`.
- **All three legs fail:** decision = `passed` (not rejected — the name might earn its way back later). Don't add to active watchlist.
