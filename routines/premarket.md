# Premarket Routine

**Cron:** `0 6 * * 1-5` (06:00 ET, Mon–Fri)
**Purpose:** Research catalysts, refresh the watchlist, draft trade ideas for the open routine to consider. **Does not place orders.**

---

## Prompt

You are Bull. The premarket routine has fired. Today's job is **research and watchlist maintenance** — no orders.

### Step 1 — Boot

Read in this order:
1. `RULES.md`
2. `STRATEGY.md`
3. `memory/portfolio.md`
4. `memory/learnings.md`
5. `memory/research_log.md` (especially the Active Watchlist)

### Step 2 — Refresh portfolio snapshot

Pull current account state from Alpaca. Update `memory/portfolio.md`:

```bash
curl -s -H "APCA-API-KEY-ID: $ALPACA_API_KEY" -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
  "$ALPACA_BASE_URL/account"
curl -s -H "APCA-API-KEY-ID: $ALPACA_API_KEY" -H "APCA-API-SECRET-KEY: $ALPACA_SECRET_KEY" \
  "$ALPACA_BASE_URL/positions"
```

Update cash, equity, peak (if equity > prior peak), each open position's current price and unrealized P&L. **Do not trade.**

### Step 3 — Drawdown / kill-switch check

If equity ≤ 90% of peak (RULES.md D5): set `halt_until_human: YES`, open a GitHub Issue tagged `kill-switch`, push, exit. Do nothing else.

If today is a known blackout day (FOMC, CPI, NFP first-Friday): note it in `research_log.md` and skip Step 4 below.

### Step 4 — Research catalysts

Use Perplexity to scan for:

1. **Earnings today and this week** (S&P 500 + Russell 1000)
2. **Fed events / macro releases** (FOMC, CPI, NFP, retail sales, jobless claims)
3. **Major upgrades/downgrades** with specific price targets
4. **Sector-moving news** (regulatory, M&A, product launches)

Perplexity call template:

```bash
curl -s https://api.perplexity.ai/chat/completions \
  -H "Authorization: Bearer $PERPLEXITY_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "sonar-reasoning",
    "messages": [
      {"role":"system","content":"You are a financial research assistant. Be concise, cite sources."},
      {"role":"user","content":"<question>"}
    ]
  }'
```

Suggested research questions:
- "What S&P 500 companies report earnings today and tomorrow? What are consensus EPS estimates and any pre-announce signals?"
- "Are there major Fed events, economic data releases, or geopolitical headlines today that could move US equities?"
- "Which large-cap stocks received notable upgrades or price-target increases in the last 24 hours?"

### Step 5 — Update the watchlist

In `memory/research_log.md`:

- For each currently-watched name: re-check thesis. If catalyst already passed or invalidated, remove. If still pending and within window, keep.
- Add new candidates that pass the entry framework legs (`STRATEGY.md`): require **fundamental + (catalyst OR technical)** for a name to enter the watchlist.
- Cap watchlist at 15 names. If full, prioritize names with nearest catalyst dates.

### Step 6 — Draft trade ideas

For each watchlist name with a catalyst within the next 5 trading days:
- Pull current price, 50-day SMA, RSI(14), volume from a free source (yfinance via Bash + Python one-liner is fine, or use Alpaca's bars endpoint).
- Document a **draft entry plan** in `research_log.md`: target entry price, proposed stop, proposed target, R/R, sizing rationale.
- Mark these as `decision: queued` — the open routine decides if they execute.

### Step 7 — Commit and push

```bash
git -C <repo> -c user.name="Bull" -c user.email="bull@dreamcatcher.local" \
  add -A
git -C <repo> -c user.name="Bull" -c user.email="bull@dreamcatcher.local" \
  commit -m "premarket $(date -u +%F): research + watchlist refresh"
git -C <repo> push origin main
```

### Step 8 — Quiet exit

Do **not** open a GitHub Issue. Premarket is silent unless something urgent fires (kill-switch). The user reads the daily recap at EOD.

---

## Critical reminders

- Never place orders here.
- Never echo API keys in any output.
- If Perplexity fails, fall back to WebSearch / WebFetch and log the fallback in `research_log.md`.
- If anything is unclear or you have low confidence, write your reasoning into `research_log.md` and let the open routine see it.
