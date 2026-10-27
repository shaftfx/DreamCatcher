# Learnings

Lessons accrued by Bull over time. Each entry is a generalizable pattern — not a single trade. Future routines read this and adjust behavior.

Format:
- Newest at top
- Date stamp + lesson + the trade(s) that taught it
- Tag with category: `[entry]` `[exit]` `[research]` `[risk]` `[ops]`

---

<!-- Example entries (replace with real ones over time):

## 2026-05-15 [entry]
Catalyst-only entries (no fundamental confirmation) underperformed +0.4% vs SPY's +1.2% over last 3 attempts. Going forward: require fundamental + (catalyst OR technical), not catalyst alone.

## 2026-05-08 [exit]
The −7% hard cut saved 2 of 3 losing positions from becoming larger drawdowns. The third (which I held past −7% by mistake) eventually went to −18%. Discipline matters; the rule works.

## 2026-04-28 [ops]
Perplexity returned a stale guidance number for $TSLA — used the actual SEC filing date as the floor for any data citation. Always cross-check against filings if guidance is in the thesis.

-->

## 2026-10-27 [research]
The 10/26 premarket wrote down NOC as "RSI 26, −9% below the 50d." Alpaca bars showed it was *above* its 50d with RSI in the 60s–70s. It also called UNH's guidance "raised" when it was only maintained. Those numbers can't be trusted unless they are computed from Alpaca bars in the same run. Don't carry technical numbers forward from a prior log entry or a web summary. Recompute SMA50, RSI and swing low from `data.alpaca.markets` bars every premarket, and cite a source for every guidance claim ("raised" vs "maintained" changes the fundamental leg).

## 2026-10-26 [ops]
The premarket volume gate (≥ 1.5× 20d avg "on entry day") can't be measured at 09:35 ET against a full-day average — the full day doesn't exist yet. Correct approach: compare today's volume since 09:30 vs. the same window over the prior 20 sessions (time-of-day relative volume), using the median not mean (earnings-day spikes inflate the mean). This is what the open routine did. The IEX-only data feed is NOT a problem for this calculation — both sides of the ratio use IEX, so it is self-consistent. On 10/26 none of the 6 queued names cleared 1.5× (best was DHR at 1.12× median) — market was genuinely quiet ahead of FOMC week. Gate worked as designed.
