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

## 2026-10-30 [risk]
Compute R/R (RULES.md P4) against the stop that is **actually live on Alpaca**, not the planned one. On 10/30, DHR/ELV/MMM targets were set at 2R off the STRATEGY 8% initial stop (entry × 1.16). S1 then swapped that stop for a 10% trailing stop, which makes the real R/R 1.6:1 on all three, below the 2:1 minimum. Until the user resolves the S1-vs-STRATEGY conflict (see weekly_review 2026-W44), set target ≥ entry × 1.20 whenever the live stop is a 10% trail. Risk $ already uses the 10% distance; the target has to match it.

## 2026-10-30 [entry]
A one-day sector rotation is not a defensive signal. On Thu 10/29, health care and industrials closed green while SPY fell, and the Fri premarket ranked DHR/ELV/MMM up for being on the "rotation side." On Friday, SPY fell 1.79% and all three fell 1.4–2.1% from their fills. Don't rank or size up on the prior day's rotation. This week's +0.42% excess came almost entirely from holding 93–100% cash on a down week, not from stock selection. Don't mistake that for edge.

## 2026-10-30 [ops]
Every gate needs exactly one routine that can measure it. STRATEGY's "volume on entry day ≥ 1.0×" can't be measured in premarket, because the day hasn't started. routines/open.md says premarket already validated it, so the 10/30 entries went in with that leg unmeasured. Premarket also wrote an ad-hoc "green on the day" condition that the open routine treated as out of scope. When a routine sees a gate that it can't measure and that no other routine owns, it should flag the gap in research_log for the user instead of assuming someone else checked it.

## 2026-10-29 [entry]
Volume gate threshold is **1.0× 20-day median (time-of-day relative volume)**, not 1.5×. STRATEGY.md always specified ≥ 20-day average. The bot self-elevated to 1.5× in early runs, causing 12/12 rejections on 10/26–10/27 in a pre-FOMC tape where even SPY was printing 0.59× median. 1.5× is for breakout/momentum entries; this strategy enters post-earnings swings where the catalyst already happened — institutional interest is confirmed by the earnings-day surge. At the open routine we need normal volume (1.0×), not elevated volume. Apply 1.0× going forward.

## 2026-10-27 [research]
The 10/26 premarket wrote down NOC as "RSI 26, −9% below the 50d." Alpaca bars showed it was *above* its 50d with RSI in the 60s–70s. It also called UNH's guidance "raised" when it was only maintained. Those numbers can't be trusted unless they are computed from Alpaca bars in the same run. Don't carry technical numbers forward from a prior log entry or a web summary. Recompute SMA50, RSI and swing low from `data.alpaca.markets` bars every premarket, and cite a source for every guidance claim ("raised" vs "maintained" changes the fundamental leg).

## 2026-10-26 [ops]
The premarket volume gate (≥ 1.5× 20d avg "on entry day") can't be measured at 09:35 ET against a full-day average — the full day doesn't exist yet. Correct approach: compare today's volume since 09:30 vs. the same window over the prior 20 sessions (time-of-day relative volume), using the median not mean (earnings-day spikes inflate the mean). This is what the open routine did. The IEX-only data feed is NOT a problem for this calculation — both sides of the ratio use IEX, so it is self-consistent. On 10/26 none of the 6 queued names cleared 1.5× (best was DHR at 1.12× median) — market was genuinely quiet ahead of FOMC week. Gate worked as designed.
