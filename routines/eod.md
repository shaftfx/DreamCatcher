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
- `spy_daily_return_pct` (fetch SPY's daily change via Alpaca bars: `GET $ALPACA_BASE_URL/stocks/SPY/bars?timeframe=1Day&limit=1`)
- `excess_vs_spy_pct` = daily_return − spy_daily_return

Update `memory/portfolio.md` with all of these.

### Step 3 — Weekly loss check (RULES.md D4)

If running 5-day return ≤ −5% from prior Friday close: set `weekly_defensive: YES`. (Reset to NO on Monday morning by premarket if conditions improved.)

### Step 4 — Compose the recap

In your head, draft the daily recap. It should answer:

1. **What happened today?** Trades placed, trades closed, today's P&L.
2. **How does the portfolio look right now?** Open positions table with cost basis, current, P&L, stop level, days held.
3. **vs SPY today and week-to-date.**
4. **Risk posture.** Any flags raised? Any rules close to triggering?
5. **What's queued for tomorrow?** Any premarket-flagged ideas the open routine will consider.
6. **One observation worth remembering.** A small lesson, even if just "my watchlist is too short, I should add 3 names tomorrow."

### Step 5 — Open a GitHub Issue

```bash
gh issue create \
  --repo shaftfx/DreamCatcher \
  --title "Recap $(date -u +%F)" \
  --label "daily-recap" \
  --body "$(cat <<EOF
## Today's P&L
- Equity: \$X,XXX (peak \$X,XXX)
- Daily return: ±X.XX%
- SPY today: ±X.XX%
- **Excess vs SPY: ±X.XX%**

## Trades placed
| Side | Ticker | Qty | Fill | Reason |
|---|---|---|---|---|
| ... |

## Trades closed
| Side | Ticker | Qty | Exit | P&L | Reason |
|---|---|---|---|---|---|
| ... |

## Open positions
| Ticker | Qty | Avg Cost | Current | Unrl P&L | Unrl % | Stop | Days |
|---|---|---|---|---|---|---|---|
| ... |

## Posture
- Halt today: <YES/NO>
- Weekly defensive: <YES/NO>
- Drawdown from peak: ±X.XX%
- New entries this week: N / 3

## Watchlist queued for tomorrow
- TICKER — thesis (catalyst <date>)

## One thing I noticed
<one paragraph>
EOF
)"
```

If `gh` is not authenticated in the cloud environment, fall back to the GitHub REST API:

```bash
curl -s -X POST -H "Authorization: token $GITHUB_TOKEN" \
  -H "Accept: application/vnd.github+json" \
  https://api.github.com/repos/shaftfx/DreamCatcher/issues \
  -d "$(jq -n --arg title "Recap $(date -u +%F)" --arg body "<body>" \
        '{title: $title, body: $body, labels: ["daily-recap"]}')"
```

(In practice, Claude Code's cloud routine has GitHub access via the same auth used for repo pushes; `gh` should work.)

### Step 6 — Reset daily flags

Set `halt_today: NO` in `portfolio.md`. (Premarket will re-evaluate weekly_defensive on Monday.)

### Step 7 — Commit and push

```bash
git add -A
git -c user.name="Bull" -c user.email="bull@dreamcatcher.local" commit -m "eod $(date -u +%F): recap + portfolio snapshot"
git push origin main
```

---

## Critical reminders

- The Issue title format is fixed: `Recap YYYY-MM-DD`. Don't deviate — the user filters by this.
- The label `daily-recap` is fixed (Friday weekly review uses `weekly-recap` instead).
- Keep the body honest. Don't paper over a losing day. The user wants signal, not optimism.
- One paragraph for "what I noticed" — not three. Brevity wins.
