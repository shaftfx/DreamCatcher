# DreamCatcher

An autonomous swing-trading bot built entirely on Claude Code routines. **Claude is the bot.** No Python service, no daemon, no servers.

Five scheduled cloud routines handle the trading day:

| Routine | Cron (ET) | Purpose |
|---|---|---|
| Pre-market | 06:00 Mon–Fri | Research catalysts, refresh watchlist |
| Market open | 09:35 Mon–Fri | Execute queued entries, set 10% trailing stops |
| Midday | 12:30 Mon–Fri | Cut −7% losers, tighten winners' stops |
| End of day | 16:15 Mon–Fri | Daily recap, post to GitHub Issues |
| Weekly review | 17:00 Friday | Full week review, self-grade, propose adjustments |

## How it works

Each routine fires on cron, clones this repo into a fresh cloud sandbox, reads the markdown files (memory + rules + strategy), does its job, updates the memory files, commits, and pushes back to `main`. The next routine reads what the previous one left behind.

**Memory lives in markdown files on `main`.** The state of the bot — current positions, trade history, research notes, accumulated learnings — is all human-readable text in this repo.

**Hard rules gate every order.** `RULES.md` is the safety system. Position sizing, daily loss caps, trailing stops, and a drawdown kill-switch are all encoded as rules every routine must respect.

## Files

| File | Purpose |
|---|---|
| `CLAUDE.md` | Agent identity ("Bull"), boot order, env vars |
| `RULES.md` | Hard pre-trade gates — non-negotiable |
| `STRATEGY.md` | Entry/exit playbook, position sizing math |
| `SETUP.md` | One-time setup walkthrough |
| `memory/` | Bot's living state (portfolio, trade log, research log, learnings, weekly review) |
| `KNOWLEDGE/` | Reference TA material (candlesticks, chart patterns, indicators, risk, psychology) distilled from the user's course |
| `routines/` | The five scheduled prompts |
| `skills/` | Reusable procedures (research a stock, place a trade, manage stops, post a recap issue) |

## Strategy in one paragraph

**Beat the S&P 500 over a 90+ day horizon by holding 5–8 fundamentally-strong US equities or ETFs at a time, sized at most 5% of equity per position with 1% capital risk per trade and a 10% trailing stop.** Entries require fundamental thesis + (catalyst within window OR clean technical setup). Hard cut at −7%, tightened stop at +15%. Daily loss cap halts trading at −2%; drawdown kill-switch at −10% from peak liquidates and waits for human re-arm.

This is **not** day trading, **not** options, **not** crypto.

## Setup

See [`SETUP.md`](./SETUP.md) for the 30-minute walkthrough.

## Status

Paper trading via Alpaca. Live capital is gated on ≥3 months of stable paper performance.

---

🐂 *Bull is autonomous. Not infallible.* Watch the GitHub Issues, read the weekly reviews, and intervene when the bot is wrong.
