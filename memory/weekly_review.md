# Weekly Review

Overwritten by the Friday weekly routine each week. Prior reviews live in git history.

## Week of 2026-11-23 → 2026-11-27 (2026-W48, Thanksgiving: 4 sessions, Fri half day)

_Written 2026-11-27 ~22:10 UTC by the weekly routine. Figures checked against Alpaca this run: account, positions, open orders, orders since 11/20, 15-min and daily portfolio history, SPY/QQQ IEX daily bars (SMA50), and Alpaca news for all 8 holdings. Trigger prompts were re-read with `list_triggers`._

### Performance
- Starting equity: $99,499.14 (Fri 11/20 close)
- Ending equity: $100,155.20 (Fri 11/27 13:00 close, EOD; Alpaca after hours $100,169.86)
- Week return: **+0.66%** (+$656.06)
- SPY week return: **+5.53%** (690.68 → 728.86, IEX). QQQ +6.73% (609.75 → 650.805)
- **Excess vs SPY: −4.87%**
- Drawdown low: $99,487.88 on the 09:30 ET Mon 11/23 15-min bar, −0.01% vs the week start and −0.98% from the $100,475.28 peak. D5 trigger ≤ $90,427.75; D1/D4 never close.
- Week high: $100,149.25 (15-min, Fri 13:00 ET). No new peak.
- Since inception (10/23 close $100,000): account **+0.16%** vs SPY −4.08% (759.83 → 728.86) → **+4.23% excess** over 5 weeks.

**Attribution (exposure vs selection).** Deployment went from 11.3% (Fri 11/20) to 16.0% (Mon) to 18.8% (Wed) to 19.0% (Fri close). Average ≈ 17%.
- **Book (positions only):** +$656 on ≈ $17.1k average capital (Modified Dietz) ≈ **+3.8%** vs SPY +5.53%.
- Per name, 11/20 close (or entry) → 11/27 close:
  - LIN +$121 (+6.0%), NOC +$109 (+5.1%), CTAS +$104 (+4.3%), DHR +$85 (+3.9%), KO +$21 (+0.8%).
  - New entries: WMT +$113 (+4.65%), TGT +$92 (+4.30%), CL +$12 (+0.46%).
  - All 8 green on the week.
- **Exposure:** ≈ 17% invested × SPY +5.53% ≈ +0.94%. So ≈ **−4.6 pts** of the −4.87% is cash.
- **Selection:** ≈ −1.7 pts on the book, ≈ **−0.3 pts** at the account level. The low-beta book lagged a +5.5% rebound, which is what it did in W46's up week too. The two Mon entries beat SPY from their fill (WMT +4.65%, TGT +4.30% vs SPY ≈ +0.6% from the Mon open). CL lagged badly: +0.46% vs SPY ≈ +4.2% from its Wed fill during the post-PCE gap.

### Trades
- Entries: **3** (C1 3/3). WMT 19 @ 127.46 and TGT 13 @ 164.89 (13/15 partial) Mon 11/23; CL 25 @ 99.30 Wed 11/25. TJX rejected Mon (4EMA inverted).
- Exits: **0**
- Wins / Losses: **0 / 0** (nothing closed)
- Avg R per closed: **n/a**
- Best (open, from entry): WMT +$112.68 (+4.65%, +0.46R vs its $242.82 original risk)
- Worst (open, from entry): DHR −$71.20 (−3.02%, −0.30R)
- Inception tally unchanged: 3 closed, 0/3, −0.43R avg, −$296.56 realized.

### Open positions (11/27 close)
| Ticker | Qty | Cost | Current | Unrl % | Days | Trail stop (hwm) | S2 line |
|---|---|---|---|---|---|---|---|
| DHR | 10 | 236.01 | 228.89 | −3.02% | 19 | 214.61 (238.45) | 219.49 |
| KO | 26 | 94.76 | 97.79 | +3.19% | 18 | 90.50 (100.56) | 88.13 |
| NOC | 4 | 540.06 | 561.47 | +3.96% | 16 | 506.60 (562.89) | 502.26 |
| CTAS | 11 | 222.48 | 229.01 | +2.94% | 13 | 207.42 (230.47) | 206.91 |
| LIN | 4 | 514.29 | 531.98 | +3.44% | 13 | 479.50 (532.78) | 478.29 |
| WMT | 19 | 127.46 | 133.39 | +4.65% | 3 | 119.87 (133.19) | 118.54 |
| TGT | 13 | 164.89 | 171.97 | +4.30% | 3 | 159.06 (176.73) | 153.35 |
| CL | 25 | 99.30 | 99.76 | +0.46% | 1 | 90.45 (100.50) | 92.35 |

- **8/8 (C2 full).** Market value $18,988.37 (19.0%), cash 81.0%. Unrealized +$451.99. Open risk, entry to trail, ≈ $1,205 (1.20%).
- All 8 GTC 10% trailing stops re-verified live on Alpaca this run (status `new`, qty = position, hwm as tabled).
- Nothing at S2 or S3 (best WMT +4.65%; S3 needs +15%).

### Step 4 — Closed trades
None closed this week. The three entries were all half-size F+T post-earnings setups, the same setup as every prior entry (11 of 11).
- **WMT:** Q3 FY27 beat with FY guide raised again. It finally got bought after the chase limit blocked it on 11/20, and it's working: hwm 133.19, Daiwa PT 113 → 140 on 11/27, the Symbotic automation expansion on 11/24.
- **TGT:** Q3 comps +5.6%, sales guide raised. It's working (hwm 176.73, +7.2% at the 11/24 peak), but it gave back 2.7% Wed–Fri. The 13/15 partial fill left ≈ 2 minutes without a stop (logged 11/23 [ops]).
- **CL:** bought into SPY's −2.7% gap after PCE. It's flat while the tape rebounded. That's a staple doing what staples do, not a broken thesis (Argus upgrade 11/23, BNP PT $112).

**Open positions, thesis check:**
- **DHR, the only real question.** 19 trading days (28 calendar days), hwm only +1.0% over entry, now −3.02%. Its trail (214.61) is 9.1% below entry and has never moved. **STRATEGY exit #5 ("flat ±3% for 30+ days → close to recycle capital") comes due Mon 11/30, the 31st calendar day.** DHR closed $0.04 under the −3% band edge (228.93). No routine prompt checks exit #5, so nothing will act on it unless someone does. With C2 at 8/8, freeing this slot is the only way the account can take MCK/TJX. My read: on Monday, if DHR is anywhere in 228.93–243.09, exit #5 calls for a close. The cleanest owner is midday, and that's a user call (proposal 1).
- **KO:** +3.19% at 25 calendar days; it reaches 30 days Wed 12/2. It's just outside the ±3% band, so exit #5 doesn't apply yet. On thesis (Coca-Cola Beverages Africa sale closed 11/27; new CFO named).
- **NOC:** on thesis. $1.13B E-130J modification 11/26, Mizuho initiation at Outperform. Trail 506.60 now 6.2% under entry.
- **CTAS:** on thesis. The **FTC/UniFirst HSR timing agreement ends Fri 12/11**, the binary event. A CNESST fatality report on Cintas Canada (11/26) isn't thesis-relevant.
- **LIN:** on thesis; best on the week (+6.0%).
- **WMT / TGT / CL:** on thesis (above).
- **No trail has crept near entry without progress.** The closest is TGT: its trail 159.06 is 3.5% under entry after a +7% run. The intermediate-S3 gap is building again on TGT, as it did on MMM.

### What worked
- **All rules held.** C1 3/3 exactly, C2 8/8, P1–P4 clean on all three entries, every fill got a 10% trail, D-flags never close, no D3 day.
- **The chase limit was vindicated.** WMT was rejected at 129.27 on 11/20 and bought Mon at 127.46, about $1.81/sh (≈ $34) better, and it's now the best name in the book.
- **Book selection was positive in absolute terms:** 8/8 green, ≈ +3.8%, and the two Mon entries beat SPY from their fill.
- **Daily attribution discipline:** every EOD split exposure from selection, so no routine read the −4.87% as a stock-picking failure or loosened gates to "catch up".
- **Calendar work:** premarket confirmed the D3 days for next fortnight from BLS: NFP Fri 12/4, then FOMC Wed 12/9 and CPI Thu 12/10 back-to-back.

### What didn't
- **−4.87% excess.** As in W46, it's mostly the deployment ceiling (half size × 8 slots ≈ 20%) in a +5.5% rebound. The book still lagged SPY by ≈ 1.7 pts on its own, though, because it's all low-beta defensives (staples, retail, materials, defense, life sciences).
- **CL timing:** bought on the gap-down day, then sat flat through a +4% index recovery. The entry passed every gate, so this isn't a gate failure. But it's another all-defensive add, which deepens the book's beta problem in up tapes.
- **Exit #5 has no owner.** It's in STRATEGY.md, but no trigger prompt checks it. It comes due for DHR on Monday.
- **Ops, still unfixed:** the `bull-open` trigger (re-read this run) still has no Step 0 and still runs `git push origin main` from its session branch. This week its 11/25 commit (CL) had to be fast-forwarded by midday. The 11/26 and 11/27 commits (0 entries each) sit only on `claude/brave-shannon-c8ymu4` / `-7p079n` (draft PRs #37, #39). Draft PRs are piling up: #12, #17, #21, #25, #28, #30, #37, #39 are open and unanswered. None of the W45–W47 proposals or the daily/weekly issues have had a user response.

### Self-grade: **D**
By the rubric this is a D: the account underperformed SPY by 4.87 pts with no rule violations. I'm not rounding it up for the same reason I didn't round W47 up to an A: the grade follows the account, and most of this week's number is the deployment ceiling, not a decision. In my favour:
- Every rule held.
- The book was 8/8 green.
- WMT/TGT beat SPY from their fill.
- The chase limit saved money on WMT.

Against:
- Even on the book alone, the selection lagged SPY by ≈ 1.7 pts.
- CL went flat into a rebound.
- Two process gaps carried into next week (exit #5 has no owner; the open routine's commits still miss `main`).

Two D's (W46, W48) in both of the account's up weeks and two B's in the down weeks: a low-beta book at ~20% deployment, doing what it was sized to do.

### 30-day framework checkpoint (STRATEGY.md "Iteration")
Inception was 10/23, so the 30-day review is due. This is the first time it's been done explicitly.
- **Result:** +0.16% vs SPY −4.08% (+4.23% excess) over 5 weeks, but almost entirely from ~80–90% cash in a falling tape. Weekly grades: W44 +0.42% (n/a), W45 B, W46 D, W47 B, W48 D. Each week's excess has been ≈ −0.85 to −1.0 × SPY's week.
- **Setup:** 11/11 entries were half-size F+T post-earnings setups. 3 closed, 0/3, −0.43R. 8 open, 7/8 green (+$452). That's **too few closed trades to judge the setup**; keep the n ≥ 10 checkpoint.
- **What's actually limiting:** deployment, not stock selection. With ~20% invested, the account can't beat SPY in an up tape. In a down tape it beats SPY by default.
- **My recommendation on the levers** (the user decides):
  1. Tie size to the regime: full size when SPY > its 50d, half below. SPY is −3.75% under its 50d (757.26) now, so the current half-size posture is right for this week.
  2. Leave C1/C2 alone until n ≥ 10 closed.
  3. Add a beta/sector note to premarket ranking so the book isn't 100% defensives when the regime flips.

### Strategy adjustments proposed (PROPOSALS — not applied)
1. **Give STRATEGY exit #5 an owner (new, urgent for Mon 11/30).** Add a midday step: "If a position is within ±3% of entry and was entered 30+ calendar days ago, close it (STRATEGY exit #5) and log the exit." It should say calendar days explicitly. DHR qualifies Mon if ≥ 228.93; KO comes due Wed 12/2.
2. **Fix where the open routine's commits go (carried from W47, still open).** Add premarket's Step 0 to `bull-open`, or change its push to `git push origin HEAD:main`, and commit the log even on zero-entry days. Then close the stale draft PRs #12/#17/#21/#25/#28/#30/#37/#39. Their content is summarized on main.
3. **Regime-scaled deployment (merges W46 #1 and W47 #3/#4).** Full size when SPY > its 50d, half size and ≤ 1 entry/week when below. This lifts the ceiling to ~40% in up tapes and keeps the W47 protection in down tapes.
4. **Intermediate S3 (carried).** 7% trail at ≥ +10%. Would have turned MMM's −$12 into ≈ +$72; TGT (+7.2% peak) is the next candidate.
5. **Codify or drop the 4EMA-stack check (carried).** It rejected TJX again on Mon.
6. **Universe-filter wording for regulatory headwinds (carried).**
7. **DST-proof the trigger crons before Sun 2027-03-14 (carried).** Re-read this run: all five are still plain UTC.

### Lessons added to learnings.md
- [exit] STRATEGY exit #5 (flat ±3% for 30+ days) had no owning routine, and DHR reaches it Mon 11/30. Each new rule needs a routine that checks it.
- [risk] Two up weeks (W46, W48) both scored D at ≈ −0.85–0.9 × SPY. At ~20% deployment in all-defensive names, the weekly score is a beta readout in both directions. Regime-scaled sizing is the lever.
- [entry] The chase limit's rejection of WMT on 11/20 led to a better fill on 11/23 (≈ $1.81/sh lower), and WMT became the book's best name. A rejected name can be re-queued at a re-based ref when its gates pass again.

### Notes for next week (2026-W49)
- **Monday item:** DHR closed 228.89, $0.04 under the ±3% band. Exit #5 is due from Mon 11/30 (31 calendar days). It needs a decision: midday under exit #5, or the user. S2 is at 219.49 (4.1% away); the trail is at 214.61.
- **Calendar:**
  - Mon 11/30 – Thu 12/3 are entry-eligible if a slot opens.
  - **Fri 12/4 NFP (D3).** **Wed 12/9 FOMC + Thu 12/10 CPI (D3, back-to-back).**
  - **CTAS: HSR timing agreement ends Fri 12/11** (FTC suit risk).
  - LOW investor day Wed 12/9.
- **Capacity:** C1 0/3 (resets Mon). **C2 8/8**: nothing can enter unless a trail fires or DHR goes on exit #5.
- **Watchlist priorities, if a slot opens:**
  - **MCK #1:** F ✅ T ✅, FY27 guide raised. A5 ADV still unverified (IEX 43k/day); confirm consolidated ADV ≥ 1M first.
  - **TJX #2:** F ✅; 4EMA stack still just inverted, closest to restacking.
  - ICE, MA, SPGI, LOW: watch-only.
- **Regime:** SPY 728.86 is −3.75% under its 50d (757.26), QQQ −7.8%. Better than last week's −9.2%, still below. Every queue should keep restating it until the user decides on regime gating (proposal 3).
