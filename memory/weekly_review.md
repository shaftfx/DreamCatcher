# Weekly Review

Overwritten by the Friday weekly routine each week. Prior reviews live in git history.

## Week of 2026-11-09 → 2026-11-13 (2026-W46)

_Written 2026-11-13 ~22:15 UTC by the weekly routine. Figures checked against Alpaca: account, positions, orders since 11/7, daily and 15-min portfolio history, SPY/QQQ IEX daily bars, and IEX 11/6 closes for the six names held into the week._

### Performance
- Starting equity: $99,952.41 (Fri 11/6 close)
- Ending equity: $100,299.56 (Fri 11/13 close, per EOD; Alpaca shows $100,351.80 after hours, mostly ELV marked 442 AH)
- Week return: **+0.35%** (+$347.15)
- SPY week return: **+2.57%** (735.40 → 754.27, IEX). QQQ +3.61% (656.31 → 680.01)
- **Excess vs SPY: −2.22%**
- Drawdown low this week: $99,971.30 at 09:45 ET Mon 11/9 (15-min history), +0.02% vs the week start. The account never closed a 15-min bar below Friday's close.
- **New peak:** $100,448.15 at 12:30 ET Thu 11/12. The EOD/midday runs missed it (they recorded $100,428.38); portfolio.md is now updated. Close is −0.15% from it; D5 trigger ≤ $90,403.34.

**Attribution (exposure vs selection).** Cash was 86% Monday morning and 81% after CTAS/LIN filled.
- **Book (positions only):** ≈ +$323 on ≈ $18.4k deployed ≈ **+1.75%** vs SPY +2.57%. Per name, 11/6 close (or entry) → 11/13 close:
  - NOC +$100 (+4.8%), KO +$92 (+3.7%), CTAS +$41 (+1.7%), LIN +$38 (+1.8%), ELV +$31 (+1.5%), DHR +$27 (+1.2%), MRK +$16 (+0.7%), MMM −$22 (−0.8%).
- **Exposure:** had the ~18% invested matched SPY, the account would have made ≈ +0.47%. So ≈ **−2.1 pts** of the −2.22% is cash drag in an up week.
- **Selection:** ≈ **−0.8 pts on the book** (≈ −0.15 pts at the account level). A defensive, low-beta book lagged a +2.6% / QQQ +3.6% rebound. 7 of 8 names were green — not bad picks, just low beta.
- **Two-week view (W45+W46, 10/30 → 11/13):** account +0.42% vs SPY −0.19% → **+0.61% excess**. Cash helped in W45 and hurt in W46 by about the same order of magnitude.

### Trades
- Entries: 2 — CTAS 11 @ 222.48 and LIN 4 @ 514.29, both Mon 11/9 (half size, F+T). Volume leg measured at the open (3.18× and 1.74×).
- Exits: 0
- Wins / Losses: n/a (no closed trades; 0 closed since inception)
- Avg R per closed trade: n/a
- Best open (whole book): KO +$115.37 (+4.68%, +0.47R vs $246 original risk)
- Worst open (whole book): DHR −$29.90 (−1.27%, −0.13R vs $236 original risk)
- This week's entries: CTAS +$41.36 (+0.17R), LIN +$37.56 (+0.18R)

### Open positions (snapshot, 11/13 close)
| Ticker | Qty | Cost | Current | Unrl % | Days | Trail stop (hwm) |
|---|---|---|---|---|---|---|
| DHR | 10 | 236.01 | 233.02 | −1.27% | 10 | 214.61 (238.45) |
| ELV | 5 | 425.85 | 432.00 | +1.44% | 10 | 403.69 (448.54) |
| MMM | 14 | 177.95 | 183.66 | +3.21% | 10 | 177.21 (196.90) |
| MRK | 16 | 148.82 | 147.76 | −0.71% | 9 | 138.03 (153.37) |
| KO | 26 | 94.76 | 99.20 | +4.68% | 9 | 89.37 (99.30) |
| NOC | 4 | 540.06 | 550.43 | +1.92% | 7 | 502.20 (558.00) |
| CTAS | 11 | 222.48 | 226.24 | +1.69% | 4 | 207.42 (230.47) |
| LIN | 4 | 514.29 | 523.68 | +1.83% | 4 | 477.18 (530.20) |

- **8/8 open (C2 full since Mon 11/9).** Market value $18,789.88 (18.7%), cash 81.3%. Total unrealized +$309.60. Open risk to trails ≈ $1,413 (1.41%).
- All 8 GTC 10% trailing stops re-verified live on Alpaca this run (status `new`).
- Nothing at S2 (−7%) or S3 (+15%).

**Thesis check:**
- All eight still on thesis. No guidance cuts, downgrades or thesis-breaking news logged this week.
- **MMM:** the stop ($0.74 under entry) got there through progress (+10.6% peak on 11/5), not drift. It has since slid to +3.2% and is 3.5% above its trail — the likeliest next exit, near breakeven. It's the only name that lost ground this week.
- **ELV:** printed 442 after hours Friday (+2.3% vs the 432 close). Cause unknown; Monday premarket should check. It also carries two of its own lawsuits (vs CMS on 2027 MA star ratings, filed 11/6).
- **CTAS:** FTC/UniFirst decision ~mid-December is the binary risk named at entry.
- **NOC:** best week (+4.8%); the post-election defense-budget worry hasn't shown up in price.
- **No position is flat long enough to trip the 30-day rule** (oldest is 10 trading days).

### What worked
- **Rules held all week.** Every gate passed on both entries: P1–P4, C1 (2/3), C2 (stopped further entries at 8/8), S1/S4 (each OTO static leg swapped to a GTC 10% trail in the same run), A1–A6, D1–D5. The CPI D3 blackout on Tue 11/10 was respected.
- **The volume leg was measured on both entries** (CTAS 3.18×, LIN 1.74×) — last week's process gap is closed. The `bull-open` trigger fired on time all week.
- **Diversification.** CTAS (industrial services) and LIN (materials) were picked over more health care; HC is 3 of 8.
- **Selection was positive in absolute terms:** 7 of 8 names up on the week, the book +1.75%.
- **Calendar work was accurate:** CPI was confirmed for Tue 11/10 (BLS) despite one outlier source saying 11/12; NFP was sourced (+165K).

### What didn't
- **The account lagged a strong up week by 2.2 pts.** This is the structural problem, not a one-off: **half-size entries × C2 = 8 slots caps deployment at ~20%**. With C2 full since Monday, the account was locked at 81% cash for the whole rebound and could not add exposure even though UNP passed every gate on 11/9. Even full-size entries under P1 (5%) would cap the account at 40%.
- **The book was low-beta on the way up too.** +1.75% vs SPY +2.57% and QQQ +3.61%. All-defensive names (staples, health care, defense, industrials) don't keep up in a rebound led by tech.
- **The intraday peak was missed.** The $100,448.15 high on 11/12 wasn't caught by midday/EOD; only a 15-min history scan found it. Harmless at −0.15% drawdown, but D5 is computed from the peak.
- **MMM keeps leaking:** +4.7% → +3.2% this week with no rule acting (still the intermediate-S3 gap).
- **None of last week's four proposals has been acted on yet** (no user commits to RULES/STRATEGY/routines since 11/6; issue #15 has no comments). The DST cron fix has a hard deadline: 2027-03-14.

### Self-grade: **D**
The rubric is clear: excess vs SPY was −2.22%, with no rule violations, so D. About 2.1 of the 2.22 pts are cash drag that the current rulebook makes unavoidable once C2 is full at half size, and the book itself was up 1.75% with 7 of 8 names green, so the decisions weren't bad. But I graded W45 down from A to B because its excess was mostly cash; the same logic has to cut the other way now, and I don't round up. Two-week excess is +0.61%, which is roughly the honest picture: the strategy has neither beaten nor lost to SPY meaningfully yet, and with 18% deployed it can't do much of either.

### Strategy adjustments proposed (PROPOSALS — not applied)
1. **Fix the deployment ceiling (new, most important).** Half-size entries in 8 slots cap the account at ~20% invested. That guarantees large negative excess in any up market and makes the score mostly a function of SPY's direction. Options for the user:
   - (a) Default to **full size** (1.0% risk, still ≤ 5% notional per P1) when F+T both pass and the name's RSI/trend are clean; keep half size for marginal setups.
   - (b) Keep half size but raise **C2 to 12** so more names can be held.
   - (c) Status quo, and accept that the account is a ~20%-beta portfolio (then compare it to 0.2 × SPY, not SPY).

   I lean (a): it doubles deployment without adding names to track, and P1/P3/S1/S2 still bound the risk per trade.
2. **Index-regime gate (still open, issue #13).** SPY recovered to 754.27 but is still ~1% under its 50d; QQQ ~4% under. Unchanged recommendation: (b), at most 1 entry/week while SPY < 50d. Note this pulls the opposite way from proposal 1 — the user should decide both together.
3. **Intermediate S3 step (carried over).** Tighten to a 7% trail at ≥ +10%. MMM is the live example again this week.
4. **DST-proof the trigger crons (carried over).** Move all five to `CRON_TZ=America/New_York` before Sun 2027-03-14.
5. **Track the intraday peak properly.** EOD should read today's 15-min portfolio history and take its max into `peak_equity`, not just the close and midday marks.

### Lessons added to learnings.md
- [risk] Half size × 8 slots caps deployment at ~20%, so in an up week the score is set by SPY's direction, not by picks. Read the excess as mostly a beta readout until the user changes sizing or C2.
- [ops] Peak equity must come from the 15-min portfolio history, not routine snapshots — W46 found an unrecorded intraday peak.

### Notes for next week (2026-W47)
- **Calendar:**
  - Mon 11/16: C1 resets to 0/3, but **C2 is 8/8** — entries only if a stop fills.
  - HD reports ~Tue 11/17; LOW and WMT ~Wed/Thu 11/18–19 (retail read-throughs; KO is the only consumer name held).
  - NVDA earnings are likely the week of 11/16 or 11/23 — confirm; it drives QQQ and the regime question.
  - Next D3: **FOMC Wed 12/9** (25 bp hike ~86% priced after hot CPI/PPI). Thanksgiving week follows (11/26 closed, 11/27 half day).
- **Open positions:**
  - MMM is 3.5% above its 177.21 trail — likeliest exit, near breakeven.
  - ELV +2.3% after hours Friday: find the cause in Monday premarket.
  - DHR (−1.27%) is the weakest; nothing near S2.
- **Watchlist priorities (if a slot opens):**
  - UNP #1 (passed every gate 11/9; only C2 blocked it).
  - TXN #2 (T holds; semis read-through from AMAT mixed).
  - SPGI #3 (F+T ✅; volume was 0.21× on 11/9, A5 near the floor).
  - TMO/UNH watch-only (HC concentration); MA/ICE watch-only until a raise is confirmed.
- **Regime:** SPY ~1% under its 50d, QQQ ~4% under. Still no regime gate pending the user's call on issue #13.
