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

## 2026-11-06 [risk] — weekly W45
Split account excess into exposure and selection every week, and grade on selection. W45 excess was +2.76%, but ≈ +2.3 pts came from holding ~86% cash on a −2.69% SPY week. The positions themselves made ≈ +0.5% on deployed capital, which is ≈ +0.4 pts at the account level. W44 was the same shape (+0.42% excess, nearly all cash). Two "positive excess" weeks in a falling tape say little about the entry framework. In the weekly review, always report book return vs SPY next to account return vs SPY. Don't let the rubric's account-level number stand in for skill.

## 2026-11-06 [ops] — weekly W45
UTC crons don't follow DST. After DST ended on 11/1, `bull-open` (still at 13:35 UTC) fired at 08:35 ET on 11/2–11/4, before the open. The run had to wait in-session, and its stale prompt skipped the volume gate on MRK/KO. The user fixed it 11/5 (now 14:35 UTC). All five triggers are now plain UTC tuned for EST, so they will fire an hour late in ET from **Sun 2027-03-14**. Before then, every trigger should use `CRON_TZ=America/New_York`. Any routine that fires and finds the Alpaca clock disagreeing with its intended ET time should flag it in its first log line.

## 2026-11-06 [exit]
A 10% trail lets a +9% winner round-trip to breakeven before S3 (+15%) ever tightens it. MMM peaked at 196.90 (+10.6% from entry) on 11/4 and closed 11/6 at 183.67 (+3.2%); its trail is 177.21, $0.74 under entry. Between +10% and +15% there's no rule that protects open gains. Don't improvise a tighter stop mid-session. If the user wants gains protected earlier, the lever is an intermediate S3 step (e.g. 7% trail at +10%), which is a RULES decision.

## 2026-11-05 [risk]
A down tape confirmed the cash lesson from the other side. On Thu 11/5, SPY fell 4.34% and the account fell only 0.24% (+4.10% excess), because 86% was cash. The positions fell 1.68%, so the selection was defensive too, but the cash did most of the work. The week went from −1.10% excess on Wed to +3.07% on Thu without a single trade. Judge excess over rolling windows, not single days, and don't credit stock-picking for what is really exposure level. Also: no index-level regime gate exists, and per-name 50d checks can still pass right after a −4% index day. Surface that to the user before redeploying. Don't invent a gate mid-session.

## 2026-11-04 [risk]
Cash drag is the mirror image of the 10/30 lesson. On Wed 11/4 the five names held overnight rose +4.26% against SPY's +1.64%, yet the account only made +0.44% because 86% sat in cash. Week to date that's −1.10% vs SPY despite positive stock selection. Half-size entries plus C1's 3/week cap mean deployment ramps slowly (~2.5% per entry), so in up tapes the account will lag the index even when picks work. Don't read a lagging up-day as bad selection, and don't loosen gates to "catch up." If the user wants less lag, the lever is sizing (full vs half) or C1, which is a RULES/STRATEGY decision for the user, not the routine.

## 2026-11-04 [ops]
Editing a file under `routines/` doesn't change what a routine actually runs. Each trigger stores its own inline copy of the prompt, so the trigger has to be updated too. On 11/3 the volume-gate ownership change went into `routines/open.md`, but the `bull-open` trigger still runs the older text, which says "Do NOT check intraday volume". That explains why the open routine kept skipping the gate. When a routine file changes, check the trigger prompt with `list_triggers` and flag any drift for the user. Better still, make the triggers `cat routines/<name>.md` so the repo is the single source.

## 2026-11-03 [ops]
Volume gate ownership: premarket cannot measure entry-day volume (session hasn't opened at 06:00 ET). Gate transferred to open routine — always checked at 09:35 ET. Premarket must not write ad-hoc blocking conditions into queued entries; context notes are fine, but the only blocking gates are STRATEGY.md legs. Both changes locked into routines/open.md, routines/premarket.md, and STRATEGY.md leg 3.

## 2026-10-30 [risk] — resolved 2026-11-03
Compute R/R (RULES.md P4) against the stop that is **actually live on Alpaca**, not the planned one. On 10/30, DHR/ELV/MMM targets were set at 2R off the STRATEGY 8% initial stop (entry × 1.16). S1 swapped that stop for a 10% trailing stop, making real R/R 1.6:1, below the 2:1 minimum. **Fixed:** RULES.md P4 now states stop distance = 10% of entry (the trailing stop S1 requires); target ≥ entry × 1.20. STRATEGY.md updated to match. Initial 8% stop is used for sizing math only; the 10% trail governs P4.

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
