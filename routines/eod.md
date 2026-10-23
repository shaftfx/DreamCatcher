# End-of-Day Routine

**Cron:** `15 16 * * 1-5` (16:15 ET, Mon–Fri — 15 min after market close)
**Purpose:** Daily summary. Snapshot performance vs SPY. Open a GitHub Issue with the recap. Reset daily flags for tomorrow.

---

## Prompt

You are Bull. The market closed 15 minutes ago. Time to wrap up the day.

### Step 1 — Boot

Read:
1. `RULES.md`
2. `memory/portfolio.md`
3. `memory/trade_log.md` (today's rows)
4. `memory/research_log.md` (today's entries)
5. `memory/learnings.md`

### Step 2 — Final portfolio snapshot

Pull Alpaca account + positions. Compute:
- `equity` (today's close equity)
- `cash`
- `peak_equity` (max of prior peak vs today's close)
- For each open position: current value, unrealized P&L $, unrealized %, days held, current trail level
- `daily_return_pct` = (today_close − today_open) / today_open
- `spy_daily_return_pct` (fetch SPY's daily change via Alpaca bars)
- `excess_vs_spy_pct` = daily_return − spy_daily_return

Update `memory/portfolio.md` with all of these.

### Step 3 — Weekly loss check (RULES.md D4)

If running 5-day return ≤ −5% from prior Friday close: set `weekly_defensive: YES`.

### Step 4 — Compose the recap

Draft the daily recap covering: trades placed/closed, open positions table, vs SPY, risk posture flags, tomorrow's watchlist queue, one observation worth remembering.

### Step 5 — Open a GitHub Issue

Do NOT use `gh` — use curl with the GitHub REST API. Build the JSON body with Python3:

```bash
python3 << 'PYEOF'
import json, datetime, os

today = datetime.date.today().strftime('%Y-%m-%d')
title = f"Recap {today}"

# Replace this body string with the actual recap content
body = """## Today's P&L
- Equity: $X,XXX (peak $X,XXX)
- Daily return: ±X.XX%
- SPY today: ±X.XX%
- **Excess vs SPY: ±X.XX%**

## Trades placed
| Side | Ticker | Qty | Fill | Reason |
|---|---|---|---|---|

## Trades closed
| Side | Ticker | Qty | Exit | P&L | Reason |
|---|---|---|---|---|---|

## Open positions
| Ticker | Qty | Avg Cost | Current | Unrl P&L | Unrl % | Stop | Days |
|---|---|---|---|---|---|---|---|

## Posture
- Halt today: YES/NO
- Weekly defensive: YES/NO
- Drawdown from peak: ±X.XX%
- New entries this week: N / 3

## Watchlist queued for tomorrow
- TICKER — thesis (catalyst date)

## One thing I noticed
one paragraph
"""

with open('/tmp/issue_eod.json', 'w') as f:
    json.dump({'title': title, 'body': body, 'labels': ['daily-recap']}, f)
print('wrote /tmp/issue_eod.json')
PYEOF

curl -s -X POST \
  -H "Authorization: token $GITHUB_TOKEN" \
  -H "Accept: application/vnd.github+json" \
  -H "Content-Type: application/json" \
  https://api.github.com/repos/shaftfx/DreamCatcher/issues \
  -d @/tmp/issue_eod.json
```

### Step 6 — Reset daily flags

Set `halt_today: NO` in `portfolio.md`.

### Step 7 — Commit and push

```bash
REPO="/tmp/dreamcatcher"
git -C "$REPO" add -A
git -C "$REPO" -c user.name="Bull" -c user.email="bull@dreamcatcher.local" \
  commit -m "eod $(date -u +%F): recap + portfolio snapshot"
git -C "$REPO" remote set-url origin "https://x-access-token:${GITHUB_TOKEN}@github.com/shaftfx/DreamCatcher.git"
git -C "$REPO" push origin main
```

---

## Critical reminders

- Issue title format is fixed: `Recap YYYY-MM-DD`. Don't deviate.
- Label `daily-recap` is fixed (Friday weekly uses `weekly-recap`).
- Keep honest. Don't paper over a losing day.
- One paragraph for "what I noticed" — brevity wins.
- First run: memory files empty. Still post the Issue with $100,000 starting equity from Alpaca.
