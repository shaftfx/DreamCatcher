# STRATEGY.md — Bull's playbook

## Mandate

Beat the S&P 500 over a 90+ day horizon by holding **5–8 high-quality US equities or ETFs at a time**, sized conservatively, with mechanical exit discipline.

Style: **fundamentals-first, catalyst-aware, swing**. Holding period ranges from a few days to a few months. Average targeted hold: 2–6 weeks.

This is *not* a trend-following or mean-reversion quant system. It's a discretionary playbook executed by an LLM that reads news, filings, and earnings calendars.

---

## Universe filters

Before any name enters the watchlist:

- US-listed common stock or ETF
- Avg daily volume ≥ 1M shares (RULES.md A5)
- Price ≥ $5 (RULES.md A6)
- Not in pre-earnings blackout (within 5 trading days of next ER)
- Sector not in active major regulatory headwind (research-driven judgment call)

The watchlist lives in `memory/research_log.md` under a `## Active Watchlist` heading. Premarket maintains it.

---

## Entry framework — three legs of confirmation

A new position requires **at least 2 of 3** to align before the open routine acts:

### 1. Fundamental thesis
- Beating earnings the prior 2 quarters with raised guidance, OR
- Sector-specific tailwind (regulatory, policy, demand shock), OR
- Reasonable valuation (P/E, P/S, or PEG within sector norms — not a high-flier we're chasing)
- Source: WebSearch + recent SEC filings via WebFetch

### 2. Catalyst within window
- Earnings, FDA, product launch, court decision, conference, fed event
- Should land within the planned hold window — entering 8 weeks before a catalyst is fine; 8 months is too far
- Source: WebSearch catalyst search + Premarket research

### 3. Technical confirmation
- Price above its 50-day SMA (uptrend baseline)
- Recent pullback to support **or** breakout from chart pattern (bull flag, ascending triangle, cup-and-handle, falling wedge — see `KNOWLEDGE/chart_patterns.md`)
- RSI between 40 and 70 (not over-extended on either side; see `KNOWLEDGE/indicators.md`)
- Volume on entry day ≥ 1.0× 20-day median (time-of-day relative volume, same window). **Do not use 1.5× — that threshold is for breakout/momentum entries and is not this strategy.**

If only the fundamental + technical legs align without a near-term catalyst, the position is sized at **half** the normal size (per P3).

---

## Position sizing math

```
risk_per_trade = 1.0% of equity         # default; tunable up to 1.5% per RULES.md P3
stop_distance  = entry_price - stop_price   # absolute $
shares         = floor(risk_dollars / stop_distance)
position_value = shares * entry_price
```

Then verify `position_value <= 0.05 * equity` (RULES.md P1). If not, scale shares down to fit.

For ETFs (lower volatility), use `risk_per_trade = 0.5%`; for high-volatility growth names, stick with 1.0%.

---

## Stop placement

- **Initial stop**: lowest of (a) recent swing low past 20 bars, (b) entry × 0.92 (8% hard floor).
- **Trailing**: 10% trailing stop on the SELL leg of the bracket order, set immediately at fill.
- **Tighten** to 7% trailing once unrealized P&L ≥ +15% (handled by midday routine).
- **Hard cut** at −7% unrealized (handled by midday routine; takes precedence over the trailing stop).

---

## Exit triggers

In priority order:

1. **Trailing stop hit** — Alpaca fills automatically. Routine logs the exit.
2. **Hard cut at −7%** — midday routine closes if trailing didn't catch it.
3. **Catalyst played out** — if the thesis catalyst happened and price reacted, take profit (or scale out 50%).
4. **Thesis broken** — if research reveals new info that invalidates the original thesis (downgrade, missed guidance, product failure), close at next routine.
5. **Held too long without progress** — if a position is flat (±3%) for 30+ days, close to recycle capital.

---

## Watchlist management

Premarket routine maintains 8–15 active candidates. Names are added when fundamental + catalyst legs align; removed when:
- Position taken (moves to `portfolio.md`)
- Catalyst passed without entry
- Thesis weakens
- 30 days without entry signal

---

## Performance benchmarks

Logged each EOD into `portfolio.md`:
- `equity` (current)
- `peak_equity` (running max)
- `daily_return_pct`
- `spy_daily_return_pct`
- `excess_vs_spy_pct` (this is the score we care about)

Weekly review writes to `memory/weekly_review.md`:
- 5-day return vs SPY
- Trades placed (count, win rate, avg R)
- Open position health
- What worked, what didn't, lessons added to `learnings.md`

---

## Iteration

The strategy is alive. After 30 days of paper trading, review whether the framework is holding up. The user (and you) can adjust:
- Risk per trade
- Concurrency limits
- Universe filters
- Catalyst weighting

Document changes in `memory/learnings.md` with a date and the reason. Old strategy versions stay in git history.
