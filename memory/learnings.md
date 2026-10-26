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

## 2026-10-26 [ops]
The premarket volume gate (≥ 1.5× 20d avg "on entry day") can't be measured literally at 09:35 ET, because the full-day volume doesn't exist yet. Alpaca's free data is also IEX-only (about 2–3% of consolidated volume). Use time-of-day relative volume instead: today's IEX volume since 09:30 vs. the same window over the prior 20 sessions, with the median alongside the mean because earnings-day spikes inflate the mean. On 10/26 none of the 6 queued names cleared 1.5× (best was DHR at 1.12× median). Premarket should either queue fewer names or set a gate the open routine can actually measure.
