# Weekly Review

Overwritten by the Friday weekly routine each week. Prior reviews live in git history.

## Week of 2026-11-16 → 2026-11-20 (2026-W47)

_Written 2026-11-20 ~22:20 UTC by the weekly routine. Figures checked against Alpaca: account, positions, open orders, orders since 11/13, 15-min and daily portfolio history, SPY/QQQ IEX daily bars, and IEX closes for the watchlist names that open rejected. Open-routine decisions for 11/19 and 11/20 were recovered from branches `claude/brave-shannon-fpht1q` (draft PR #28) and `claude/brave-shannon-0bpiog` (draft PR #30); see "Ops" below._

### Performance
- Starting equity: $100,299.56 (Fri 11/13 close)
- Ending equity: $99,499.14 (Fri 11/20 close, EOD; Alpaca after hours $99,501.70)
- Week return: **−0.80%** (−$800.42)
- SPY week return: **−8.43%** (754.27 → 690.68, IEX). QQQ −10.33% (680.01 → 609.75)
- **Excess vs SPY: +7.63%**
- Drawdown low: $99,499.14 at the Fri close, −0.80% vs the week start and −0.97% from the $100,475.28 peak (15-min low $99,513.94 on the 16:00 ET bar). D5 trigger ≤ $90,427.75; D4 (−5% weekly) never close.
- Week high: $100,430.58 at 10:15 ET Mon 11/16 (15-min). No new peak.
- Since inception (10/23 close $100,000): account −0.50% vs SPY −9.10% (759.83 → 690.68) → **+8.60% excess** over 4 weeks.

**Attribution (exposure vs selection).** The account started the week 18.7% invested ($18,789.88 in 8 names) and ended 11.3% invested.
- **Book (positions only):** −$800 on $18.8k ≈ **−4.26%** vs SPY −8.43% / QQQ −10.33%. Per name, 11/13 close → 11/20 close (or exit):
  - MRK −$156 (exit), ELV −$142 (exit), DHR −$127, MMM −$92 (exit), LIN −$88, CTAS −$74, NOC −$64, KO −$57. All 8 red.
- **Exposure:** if the 18.7% invested had matched SPY, the account would have been ≈ −1.58%. So ≈ **+6.85 pts** of the +7.63% is cash.
- **Selection:** ≈ **+4.2 pts on the book** (≈ +0.78 pts at the account level). The defensive book fell about half as much as SPY in a −8% week. That's real, but it's mostly low beta, which is the same reason it lagged by 0.8 pts in W46's up week.

### Trades
- Entries: **0**. 6 names were queued across Thu/Fri; the open routine rejected all 6 (details below). C1 0/3.
- Exits: **3**, all 10% trailing stops.
- Wins / Losses: **0 / 3** (first closed trades since inception)
- Avg R per closed: **−0.43R** (realized −$296.56 on $703 original risk; −0.30% of equity)
- Best: MMM (−$12.19, −0.05R)
- Worst: MRK (−$173.12, −0.73R)

| Exit | Ticker | Qty | Entry → Exit | P&L | R | Held | Trigger |
|---|---|---|---|---|---|---|---|
| Wed 11/18 | ELV | 5 | 425.85 → 403.60 | −$111.25 (−5.2%) | −0.52 | 13d | trail 403.69 (hwm 448.54) |
| Wed 11/18 | MRK | 16 | 148.82 → 138.00 | −$173.12 (−7.3%) | −0.73 | 12d | trail 138.03 (hwm 153.37) |
| Thu 11/19 | MMM | 14 | 177.95 → 177.08 | −$12.19 (−0.5%) | −0.05 | 20d | trail 177.21 (hwm 196.90) |

**What the open routine rejected** (decisions recovered from the unmerged branches):

| Day | Ticker | Reason | Ref/live → 11/20 close | Avoided (approx.) |
|---|---|---|---|---|
| Thu 11/19 | UNP | volume 0.40× | 296.91 → 287.21 | ≈ −$78 |
| Thu 11/19 | TXN | volume 0.53× + above chase | 299.60 → 263.95 (−11.9%) | ≈ −$240 (trail would have hit ≈ 269.6) |
| Thu 11/19 | TJX | 4EMA stack inverted | 138.48 → 139.69 | ≈ +$20 (missed) |
| Fri 11/20 | TJX | above chase (142.20 vs 141.58) | 142.20 → 139.69 | ≈ −$43 |
| Fri 11/20 | WMT | above chase (129.27 vs 127.93) | 129.27 → 128.04 | ≈ −$23 |
| Fri 11/20 | UNP | 4EMA stack broken | 293.72 → 287.21 | ≈ −$52 |

Net, the open-routine gates kept ≈ $400 (≈ 0.4% of equity) off the table in a −8% week.

### Open positions (11/20 close)
| Ticker | Qty | Cost | Current | Unrl % | Days | Trail stop (hwm) | S2 line |
|---|---|---|---|---|---|---|---|
| DHR | 10 | 236.01 | 220.36 | −6.63% | 15 | 214.61 (238.45) | 219.49 |
| KO | 26 | 94.76 | 97.00 | +2.36% | 14 | 90.50 (100.56) | 88.13 |
| NOC | 4 | 540.06 | 534.31 | −1.06% | 12 | 502.20 (558.00) | 502.26 |
| CTAS | 11 | 222.48 | 219.53 | −1.33% | 9 | 207.42 (230.47) | 206.91 |
| LIN | 4 | 514.29 | 501.72 | −2.44% | 9 | 477.32 (530.35) | 478.29 |

- **5/8 open.** Market value $11,284.52 (11.3%), cash 88.7%. Total unrealized −$204.10. Open risk to trails ≈ $878 (0.88%).
- All 5 GTC 10% trailing stops re-verified live on Alpaca this run (status `new`; hwm unchanged).
- Nothing at S3. **DHR is 0.4% above S2.**

### Step 4 — Closed trades, one by one
- **ELV:**
  - Entry framework: F+T half size; held up at entry (Q3 beat, FY guide raised, above 50d).
  - Catalyst: none forward. The print had already happened. What arrived instead was the CMS CRUSH Medicare Advantage audit proposal (11/17), a sector regulatory shock. ELV was already suing CMS over star ratings, so managed care had a live regulatory headwind at entry, which the universe filter says to avoid. That was a judgment miss, not a rule breach.
  - Exit: correct. The trail fired at −5.2% before S2 was needed.
- **MRK:**
  - Entry framework: F+T half size; held up at entry.
  - Catalyst: none. It lost the 50d on 11/16, and the BELLWAVE program was discontinued 11/17. Premarket flagged both as weakening but didn't call the thesis broken (exit trigger #4). Selling at the 11/18 open (≈ 141.79) instead of the trail (138.00) would have saved ≈ $61. One pipeline cut doesn't clearly break a beat-and-raise thesis, so I'd make the same call again. But the record should say it cost $61.
  - Exit: correct by rule. The fill was within 3¢ of the trail, at the 14:00 ET FOMC-minutes print.
- **MMM:**
  - Entry framework: F+T half size; worked. It ran to +10.6% (hwm 196.90) by 11/4.
  - Catalyst: none forward.
  - Exit: correct by rule, but the rule left money on the table. With the proposed intermediate S3 (7% trail at ≥ +10%), the stop would have been 183.12 and the exit ≈ +$72 instead of −$12, about **$85 better**. That's the third week this gap has shown up.

**Pattern:** all 3 losers were post-earnings F+T entries with no forward catalyst, held 12–20 days through a sector-led selloff. n=3 is too small to call the catalyst-less half-size setup broken, but it is the only setup the account has ever traded (8 of 8 entries). Once 10 have closed, compare its hit rate and avg R before the user widens deployment.

**Open positions, thesis check:**
- **DHR:** −6.63%, 15 days, hwm only +1.0% over entry. It's drifting without progress, not creeping. Its trail (214.61) sits *below* S2 (219.49), so **Mon midday must cut it if it's ≤ −7%.** Thesis (life-sciences recovery) not broken by news (Microsoft lab-automation partnership 11/20), but price says otherwise.
- **KO:** on thesis, the only green name.
- **NOC:** on thesis; −1.1%.
- **CTAS:** on thesis. The FTC/UniFirst suit is still the binary risk; HSR timing agreement runs to **Dec 11**.
- **LIN:** on thesis (Kepler upgrade 11/19); −2.4%.
- **No trail is near entry without progress.** All five trails sit 6–10% under entry.

### What worked
- **Every rule held through the worst week since inception:**
  - The trails exited three names for −0.30% of equity total, each loss ≤ 0.17% of equity.
  - D1/D4/D5 never close; S2 never needed.
  - C1 unused; P1–P4 clean on everything queued.
- **The open routine's gates did what the missing regime gate couldn't.** Volume, chase limit and the 4EMA check rejected all 6 queued names; TXN alone would have fallen 11.9% from its would-be fill. Each rejection was logged with numbers, and the routine didn't re-read volume later to manufacture a pass.
- **Premarket's regime awareness:** on Fri it deliberately queued 2 of 3 open slots and stated the regime risk on every name.
- **Defensive selection:** book −4.26% vs SPY −8.43%.
- **Research process:** EDGAR 8-Ks for guidance claims (TJX/WMT/LOW), Alpaca news for same-day causes (CMS CRUSH). The LOW tariff-refund beat was correctly not counted as a raise.

### What didn't
- **0 for 3 on closed trades, −0.43R average.** All three were catalyst-less post-earnings holds that the sector tide took out.
- **ELV was entered into a sector with a live regulatory dispute,** and the universe filter should have caught it.
- **MMM round-tripped a +10.6% gain to −0.5%.** This is the intermediate-S3 gap, now costed at ≈ $85.
- **Ops: open-routine records never reached `main`.** Midday and EOD on 11/19–11/20 logged the open routine as "silent, no commit". It did commit and push, but to its session branch. **6 of 10 open-routine commits since 11/5 are only on `claude/brave-shannon-*` branches**, sitting in unmerged draft PRs #12, #17, #21, #25, #28, #30. Probable cause: the `bull-open` trigger has no Step 0 that clones `main` to `/tmp/dreamcatcher`, as premarket does. It works in the session checkout and runs `git push origin main`, which doesn't push the session-branch HEAD. Its Step 7 ("exit silently") adds to the confusion.
- **A gate drifted from the docs:** the `bull-open` trigger checks a "4EMA stack" that STRATEGY.md leg 3 doesn't list. It's protective (it rejected TJX and UNP), but it's a gate the user never wrote into the playbook.

### Self-grade: **B**
By the letter of the rubric this is an A: +7.63% excess, no rule violations, learnings logged. I'm not taking it. In W45 I cut a cash-driven +2.76% from A to B, and in W46 I wouldn't round a cash-driven −2.22% up. The same logic applies here. About 6.85 of the 7.63 pts came from holding 81–89% cash during an −8.4% SPY week, which is the rulebook's deployment ceiling, not a decision I made. What I can claim:
- The book beat SPY by 4.2 pts.
- Every exit was mechanical and small.
- The open gates avoided ≈ $400 of entries into the slide.

Against that:
- All three closed trades lost.
- ELV went into a sector with a live regulatory fight.
- The account's own records were split across six unmerged branches without anyone noticing for two weeks.

Good risk control and decent decisions, with a selection record that isn't proven yet: a B.

### Strategy adjustments proposed (PROPOSALS — not applied)
1. **Fix where the open routine's commits go (new, ops, most urgent).** Give `bull-open` the same Step 0 as premarket (clone/pull `main` into `/tmp/dreamcatcher` and work there), or change its push to `git push origin HEAD:main`. Change Step 7's "exit silently" to "commit and push the rejection log regardless". Then merge or close draft PRs #12/#17/#21/#25/#28/#30; their content is summarized in research_log so closing them loses nothing material. Check `bull-midday` too: it also lacks Step 0, though its commits have been reaching main.
2. **Codify or drop the 4EMA-stack check (new).** It's in the open trigger prompt but not in STRATEGY.md leg 3. I lean toward codifying it, since it rejected TJX/UNP correctly this week, so the playbook and the executor agree.
3. **Index-regime gate (issue #13, still open, now urgent).** SPY is **−9.2% under its 50d** (760.21) and QQQ −14.2%. Per-name gates found 6 candidates in this tape. The open routine's gates caught them, but by luck of construction. Recommendation unchanged: at most 1 new entry/week while SPY < its 50d.
4. **Deployment ceiling (W46 #1, still open).** This week shows the other side: the ~20% ceiling saved ≈ 6.9 pts. Decide it together with #3, for example full size only when SPY > its 50d and half size below it.
5. **Intermediate S3 (carried, now costed).** A 7% trail at ≥ +10% would have turned MMM's −$12 into ≈ +$72.
6. **Universe filter: name the managed-care/MA regulatory risk explicitly (new, small).** "Active major regulatory headwind" should include a pending CMS rule or lawsuit against the regulator. ELV had both at entry.
7. **DST-proof the trigger crons (carried).** Move all five triggers to `CRON_TZ=America/New_York` before Sun 2027-03-14.

### Lessons added to learnings.md
- [ops] "Silent" routine ≠ no commit: check `git branch -r` for `claude/*` branches and open draft PRs before calling a routine silent. 6 of 10 open-routine commits never reached main.
- [entry] In a sub-50d tape, the open routine's chase/volume/EMA gates rejected 6/6 queued names and avoided ≈ $400. Don't loosen chase limits or re-read volume to get a fill, and don't let premarket's "passes all gates" stand in for a regime check.
- [exit] First 3 closed trades: 0/3, −0.43R, all catalyst-less F+T holds exited by the trail. The intermediate-S3 gap is now quantified (MMM ≈ $85).

### Notes for next week (2026-W48, Thanksgiving)
- **Monday item:** DHR closed 220.36, 0.4% above S2 (219.49). Mon midday cuts it if it's ≤ −7%; its trail (214.61) won't catch it.
- **Calendar:**
  - No D3 day. Thu 11/26 closed; Fri 11/27 closes 13:00 ET.
  - Earnings: ZM Mon AMC; MDT/ADI Tue BMO; WDAY/DELL/HPQ Tue AMC; DE Wed.
  - Wed 11/25 08:30: Q3 GDP 2nd estimate + October PCE, a rates mover with a Dec hike priced.
  - Next D3: **FOMC Wed 12/9**; Nov NFP presumably Fri 12/4 (confirm).
  - CTAS: HSR timing agreement ends **Dec 11** (FTC suit risk).
- **Capacity:** C1 0/3, C2 5/8 (6/8 slots free if DHR is cut).
- **Watchlist priorities:**
  - **WMT #1:** F+T ✅; was only blocked by the chase; closed 128.04. Re-base the entry ref.
  - **TJX #2:** chase-blocked; 4EMA stack still inverted.
  - **UNP:** watch-only until its EMA stack repairs; 287.21 is now under its 50d (≈ 288), so premarket's "drop if under 50d" rule applies.
  - **TXN:** drop. It closed 263.95, well under its 50d.
  - SPGI, TMO, ICE, MA, LOW: watch-only as before.
- **Regime:** SPY −9.2% under its 50d, QQQ −14.2%, after an −8.4% week. Every queue should restate it until the user rules on #13.
