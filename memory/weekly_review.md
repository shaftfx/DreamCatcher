# Weekly Review

Overwritten by the Friday weekly routine each week. Prior reviews live in git history.

## Week of 2026-11-02 → 2026-11-06 (2026-W45)

_Written 2026-11-06 ~22:15 UTC by the weekly routine. Figures were checked against Alpaca: account, open orders, closed orders, daily and 15-min portfolio history, and SPY IEX daily bars._

### Performance
- Starting equity: $99,882.75 (Fri 10/30 close, Alpaca `last_equity` / portfolio history)
- Ending equity: $99,952.41 (Fri 11/6 close, per EOD; $99,971.45 after hours)
- Week return: **+0.07%** (+$69.66)
- SPY week return: **−2.69%** (755.72 → 735.40, IEX)
- **Excess vs SPY: +2.76%**
- Drawdown low this week: $99,768.73 at 15:45 ET Tue 11/3 (Alpaca 15-min history). That's −0.11% vs the week start and −0.23% vs the peak at the time ($100,000).
- Intraday high: $100,428.38 at 10:15 ET Thu 11/5. This is above the $100,294.01 peak recorded in portfolio.md, which is now updated to it. From that high to Friday's close is −0.47%, nowhere near D5 (−10%).

**Attribution (exposure vs selection).** The account was 86–88% cash all week.
- **Exposure:** if the ~13% invested had simply matched SPY, the account would have lost ≈ 0.35%. That puts **≈ +2.3 pts** of the +2.76% excess down to cash.
- **Selection:** the positions themselves made ≈ +$72 on roughly $12–14k deployed (≈ +0.5%) while SPY fell 2.69%. That's **≈ +0.4 pts** of real selection edge at the account level.
- **Day by day, the book was not consistently low-beta:**
  - Wed 11/4: book +4.26% vs SPY +1.64%.
  - Thu 11/5: book −1.68% vs SPY −4.34%, in the AI/chip selloff.
  - Fri 11/6: book −0.39% vs SPY +0.27%.

### Trades
- Entries: 3. MRK 16 @ 148.82 and KO 26 @ 94.76 on Mon 11/2; NOC 4 @ 540.06 on Wed 11/4. All half size (F+T, no near-term catalyst).
- Exits: 0
- Wins / Losses: n/a (no closed trades)
- Avg R per closed trade: n/a
- Best open (whole book): MMM +$80.08 (+3.21%, +0.32R vs $249 original risk). Its week move from the 10/30 close was +$133.
- Worst open (whole book): NOC −$60.20 (−2.79%, −0.27R vs $221 original risk)
- This week's entries: KO +$24.11 (+0.10R), MRK −$32.80 (−0.14R), NOC −$60.20 (−0.27R)

### Open positions (snapshot, 11/6 close)
| Ticker | Qty | Cost | Current | Unrl % | Days | Trail stop (hwm) |
|---|---|---|---|---|---|---|
| DHR | 10 | 236.01 | 230.25 | −2.44% | 5 | 214.61 (238.45) |
| ELV | 5 | 425.85 | 425.62 | −0.05% | 5 | 403.69 (448.54) |
| MMM | 14 | 177.95 | 183.67 | +3.21% | 5 | 177.21 (196.90) |
| MRK | 16 | 148.82 | 146.77 | −1.38% | 4 | 138.03 (153.37) |
| KO | 26 | 94.76 | 95.69 | +0.98% | 4 | 87.65 (97.39) |
| NOC | 4 | 540.06 | 525.01 | −2.79% | 2 | 485.75 (539.72) |

- 6/8 open (C2). Market value $13,938 (13.9% of equity), with 86.1% in cash. Total unrealized −$47.56.
- All 6 GTC 10% trailing stops were re-verified live on Alpaca at this run (status `new`).
- Nothing is at S2 (−7%) or S3 (+15%).
- **Sector mix:** health care 3 (DHR/ELV/MRK), plus industrials (MMM), staples (KO) and defense (NOC).

**Thesis check:**
- All six are still on thesis. No guidance cuts, downgrades or thesis-breaking news were logged this week.
- **NOC:** the Democratic sweep on 11/3 is headline risk for defense, but it isn't a thesis break, because the new Congress isn't seated until January.
- **MMM:** its stop is near entry, but it got there through progress, not drift. It ran +10.6% to 196.90 on 11/4–11/5 and gave most of it back, so the trail now sits $0.74 under entry. It's the clearest case for an intermediate S3 step (proposal 2).
- **No stop has crept up to entry without progress.**
- DHR (−2.44%) and NOC (−2.79%) are the weakest. Both are more than 4 pts from S2.

### What worked
- **Rules held all week.** Every gate passed on every entry:
  - Sizing: P1, P2, P3.
  - P4: target is entry × 1.20 vs the live 10% trail.
  - Concurrency: C1 reached 3/3 and then stopped entries on Thu and Fri; C2.
  - Stops: S1/S4 (every static OTO leg was swapped for a GTC 10% trail in the same run).
  - Scope (A1–A6) and the loss caps (D1–D5).
  - The NFP D3 blackout on Fri was respected.
- **Last week's three proposals were all implemented by the user** (775c367, ddd49e1):
  - P4/S1 resolved: targets are now entry × 1.20.
  - The volume gate is now owned by the open routine.
  - Premarket no longer adds its own blocking conditions.
- **The `bull-open` trigger was fixed on 11/5.** It now fires at 14:35 UTC (09:35 ET), and its prompt is synced with the volume gate. I confirmed both with `list_triggers` this run. The premarket, midday, EOD and weekly crons also map correctly to ET now.
- **The open run waited for the market to open.** On 11/2 and 11/4 the mis-timed trigger fired before the open. Both times the run waited in-session until 09:35 ET before validating anything, so no pre-open fills.
- **Diversification away from health care.** NOC was picked over the third health-care name. Premarket has blocked new health-care entries while HC is 3 of 6.
- **Defensive selection on the −4.3% day.** On Thu 11/5 the book fell 1.68% vs SPY's −4.34%.

### What didn't
- **Most of the excess is exposure, not edge.** Of the +2.76%, about 2.3 pts came from holding ~86% cash during a −2.69% SPY week. This is the same pattern as W44. Two weeks of positive excess say very little about the entry framework yet.
- **MRK and KO went in with STRATEGY leg 3 partly unmeasured.** On 11/2 the stale `bull-open` prompt said "Do NOT check intraday volume", and the run followed it. NOC on 11/4 was measured (3.60×). It isn't a RULES breach, but two of three entries took the volume leg on trust.
- **MMM gave back most of a +10.6% run.** It peaked at 196.90 and closed at 183.67. With a 10% trail and S3 only kicking in at +15%, nothing protects gains between +10% and +15%.
- **The account lagged the up days.** Wed 11/4 was −1.20% excess and Fri 11/6 was −0.32%. That is cash drag at half-size deployment, as expected (learnings 2026-11-04).
- **The NFP print is still unsourced.** EOD couldn't find it, so Mon premarket has to get it before reading anything into Friday's tape.
- **The watchlist is down to 5 names**, below STRATEGY's 8–15, and only 2 are live candidates (CTAS, UNP).

### Self-grade: **B**
Taken literally, the rubric gives an A: excess was +2.76% (≥ +1%), no RULES.md gate was breached, and learnings were logged. I'm marking it down to B for two reasons:
1. **Most of the excess isn't skill.** Roughly 2.3 of the 2.76 pts came from being 86% cash in a falling market. Holdings selection added only about +0.4 pts.
2. **The process wasn't clean.** On 11/2, MRK and KO were bought without measuring the entry-day volume leg, because the trigger prompt was out of date. And MMM's +10% unrealized gain was mostly given back.

The decisions themselves were sound: discipline on C1, D3 and S1, the move toward non-HC names, and waiting out the mis-timed open trigger. So B, not A. Last week's C is now a B mainly because the rulebook conflicts were fixed, not because the picks got better.

### Strategy adjustments proposed (PROPOSALS — not applied)
1. **Index-regime gate (still open from issue #13).** SPY closed 11/6 at 735.40, about 4% under its 50d, RSI ~34; QQQ is ~10% under its 50d. A name can pass its own 50d check right after a −4% index day. Choose one:
   - (a) allow no new entries while SPY closes below its 50d SMA;
   - (b) allow at most 1 entry per week while SPY is below its 50d;
   - (c) keep the status quo, since half sizing and C1 already throttle deployment.

   I lean (b): it keeps the account learning without adding exposure into a falling index.
2. **Intermediate S3 step.** At ≥ +10% unrealized, tighten the trail from 10% to 7%. Keep S3 at +15% as-is, or move it to 5%. Evidence: MMM peaked at +10.6% and its 10% trail sat near breakeven. A 7% trail from 196.90 would have been 183.12, locking in about +2.9%. This is a RULES change, so it's the user's call.
3. **Report exposure vs selection every week.** Add "book return vs SPY" next to "account excess vs SPY" in STRATEGY's performance benchmarks. Grading on account excess alone rewards holding cash in down weeks and penalizes it in up weeks.
4. **Make trigger crons DST-proof.** All five triggers are now plain UTC, set for EST. On **Sun 2027-03-14** (DST starts) every one of them will fire an hour late in ET: open at 10:35 ET, EOD at 17:15 ET. Rewrite them as `CRON_TZ=America/New_York …` before then.

### Lessons added to learnings.md
- [risk] Every week, split account excess into an exposure part and a selection part. Grade on the selection part.
- [ops] UTC crons don't follow DST. The triggers are correct for EST now and will drift again on 2027-03-14 unless they move to CRON_TZ.

### Notes for next week (2026-W46)
- **Calendar:**
  - Mon 11/9 is an entry day. C1 resets to 0/3; C2 is 6/8, so at most 2 entries.
  - **The October CPI release date must be confirmed by Mon premarket.** It is likely mid-week and is a D3 blackout.
  - Get the actual Fri 11/6 NFP print and the market's read on December rate-hike odds (~80% priced per Reuters before the print).
- **Open positions:**
  - MMM is 3.6% above its 177.21 trail, with a breakeven-ish stop.
  - NOC (−2.79%) and DHR (−2.44%) are the weakest; watch S2 at midday.
  - Watch NOC for defense-budget headlines.
- **Watchlist priorities:**
  - CTAS is #1: F+T ✅, RSI 64.7, with an FTC/UniFirst decision ~mid-Dec. It was rejected 11/4 only on the chase limit.
  - UNP is #2: F+T ✅, RSI cooled to 55.
  - TMO and UNH are watch-only because of health-care concentration.
  - TXN was demoted after a −10.7% day; drop it if it closes under 272.
  - **Premarket must add 3+ non-health-care names** to get back to 8–15. Recompute every technical from fresh Alpaca bars.
- **Regime:** SPY and QQQ are below their 50d. Until the user rules on proposal 1, treat Mon entries with extra scrutiny and prefer the stronger of the two candidates over taking both.
