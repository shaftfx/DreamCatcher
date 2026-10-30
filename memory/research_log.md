# Research Log

Dated entries. Premarket appends new research; other routines append rejected ideas, thesis updates, and rule violations.

## Active Watchlist

_Last refresh: 2026-10-30 premarket (Fri). Technicals recomputed this run from Alpaca IEX daily bars through the 10/29 close. **Today is an entry day** (not a D3 blackout; NFP first-Friday is 11/6). Tape is risk-off: S&P futures about −0.9% and Nasdaq-100 about −2% on AMZN/INTC, hot September PCE (headline +3.6% y/y), Brent above $117, and December hike bets. Thursday's rotation was *into* health care, industrials and staples, and every active name closed up on 10/29 while SPY fell 0.36%. Six names are `decision: queued half` (F+T, no dated catalyst within 5 days). Gate unchanged: time-of-day relative volume ≥ 1.5× (median of prior 20 sessions). C1: 0/3 this week. At most one of UNH/ELV._

| Ticker | Added | Thesis (1 line) | Catalyst | Catalyst Date | Status (10/29 close · SMA50 · RSI14 · 20-bar swing low) |
|---|---|---|---|---|---|
| DHR | 2026-10-26 | Q3 beat+raised, life-sciences recovery | none within 8w | — | **queued half #1**, F+T ✅ — 236.98 · 218.54 (+8.4%) · 64.9 · 211.72; closed at a 20-day high |
| CTAS | 2026-10-29 | Q1 FY27 beat, FY27 guide raised (8-K) | Q2 FY27 earnings (~late Dec, unconfirmed); FTC review of UniFirst deal | ~late Dec | **queued half #2**, F+T ✅ — 218.00 · 204.13 (+6.8%) · 60.1 · 191.85 |
| ELV | 2026-10-27 | Q3 beat, FY26 adj EPS guide raised to ≥ $29.00 | none within 8w | — | **queued half #3**, F+T ✅ (recovered) — 422.00 · 410.08 (+2.9%) · 52.0 · 381.21. Preferred over UNH |
| MMM | 2026-10-26 | Q3 beat ($2.50 vs $2.39), FY guide raised to $9.10–9.15 | none within 8w | — | **queued half #4**, F+T ✅ — 177.38 · 168.54 (+5.2%) · 65.0 · 159.49; at a 20-day high |
| UNP | 2026-10-26 | Q3 beat, rail pricing power | none within 8w | — | **queued half #5**, F+T ✅ but near limit — 301.90 · 287.46 (+5.0%) · RSI 68.1 · 273.69 |
| NOC | 2026-10-26 | Q3 beat+raised (FY adj EPS $29.35–29.75) | US midterms 11/3 (event *risk*, not a thesis catalyst) | 2026-11-03 | **queued half #6**, F+T ✅ — 562.41 · 520.49 (+8.1%) · 66.7 · 470.54 |
| UNH | 2026-10-26 | Q3 beat ($4.69); FY guide *maintained* ~$20.50 | none within 8w | — | active, F+T ✅ — 410.91 · 389.74 (+5.4%) · 59.2 · 364.64. **Alternate only**: take UNH only if ELV fails its gate/chase and C1 has room |
| TXN | 2026-10-26 | Q3 beat ($2.62 vs $2.42); Q4 guide $5.8–6.3B / EPS $2.45–2.79 | none within 8w | — | watch-only. Technical fails: 312.92 · 274.94 (+13.8%) · RSI 71.8. Semis −1.4% 10/29 and INTC −20%+ AH; revisit on a pullback |

_Removed: none. Re-checked and not added: PH 928.84 vs SMA50 958.16 (−3.1%), RSI 46.3 → technical fails. Still stretched: ROP (RSI 78.7, +14.9% vs 50d), LMT (RSI 79.1, +18.6%)._

---

## Week flags (2026-11-02 week)

- **Mon 11/2:** AAPL reports after close (per one preview). Entry day.
- **Tue 11/3:** US midterm elections. Not a D3 blackout, but a binary event for defense (NOC) and managed care (UNH/ELV). Treat as cautious; prefer no new NOC/UNH/ELV entries that day.
- **Wed 11/4:** post-election reaction. Entry day if the tape settles.
- **Fri 11/6:** NFP first-Friday → **D3 blackout**, no new entries.
- **DST ends Sun 11/1:** UTC crons shift one hour earlier in ET from Monday.

## Week flags (2026-10-26 week, closing)

- Tue 10/27 entry day (0 entries, volume gate); Wed 10/28 FOMC blackout; Thu 10/29 GDP/PCE no-entry; **Fri 10/30 entry day** (this premarket queues).

---

## Research Entries

### 2026-10-27 05:45 UTC — PREMARKET — DATA CORRECTION (read before acting on 10/26 entries)

The 10/26 premarket entries contain numbers that don't match Alpaca's daily bars. Recomputed from the IEX bars (Jun 1 → Oct 26 close):
- **NOC:** the 10/26 entry said "RSI 26, −9% from 50d". As of the 10/23 close NOC was $551.62 against a ~$520 50d SMA, so it was *above* its 50d then too. At the 10/26 close: $565.67, SMA50 $522.03 (+8.4%), RSI 71.6. The "oversold" thesis was wrong. NOC is moved to watch-only.
- **UNH:** "beat and raised" is wrong. UNH *maintained* its FY26 guide (~$20.50 EPS). The fundamental leg still passes on the beat, plus RBC (PT $498) and Mizuho (PT $500) target raises.
- Lesson logged in learnings.md.

### 2026-10-27 05:45 UTC — PREMARKET — WATCHLIST REFRESH (all names)

**Account:** paper, equity $100,000.00, cash = buying power, multiplier 1 (A4 ✅). 0 positions, 0 open orders. Peak $100,000; D5 clear. No halt flags.

**Research sources and fallback:** Perplexity wasn't used; WebSearch only. Results for same-day upgrades and the full weekly earnings calendar were **thin**: no 2026 calendar list was found, and no 10/26-dated upgrade roundup. The open routine shouldn't treat the absence of news as confirmation.

**Technicals (10/26 close, IEX daily bars; RSI is Wilder 14; stop = max(20-bar swing low, entry × 0.92); half size = 50% of the P1 5% cap ≈ $2,500):**

| Ticker | Close | SMA50 | vs 50d | RSI14 | 20-bar swing low | Last candle | Legs (F/C/T) |
|---|---|---|---|---|---|---|---|
| TXN | 298.02 | 272.76 | +9.3% | 64.4 | 272.13 | +4.65% wide-range up day, close near high | ✅/❌/✅ |
| DHR | 233.01 | 216.76 | +7.5% | 61.9 | 211.20 | +1.1%, normal | ✅/❌/✅ |
| UNP | 296.96 | 287.48 | +3.3% | 65.8 | 268.73 | +1.4%, close at high | ✅/❌/✅ |
| ELV | 431.37 | 408.67 | +5.6% | 58.8 | 376.19 | −2.0%, opened at high and closed near low (bearish-ish) | ✅/❌/✅ (watch the candle) |
| UNH | 410.45 | 388.72 | +5.6% | 59.7 | 362.66 | −1.8%, opened at high and closed near low (bearish-ish) | ✅/❌/✅ (watch the candle) |
| MMM | 172.77 | 168.94 | +2.3% | 59.2 | 159.49 | −0.4%, small body | ✅/❌/✅ |
| NOC | 565.67 | 522.03 | +8.4% | 71.6 | 470.54 | +2.5% up day | ✅/❌/❌ (RSI > 70) → watch |

The technical leg here covers only price above the 50d and RSI. The volume part of the leg is checked live at the open using the time-of-day method.

**Fundamentals checked today:**
- **TXN:** Q3 rev ~$6.05B vs $5.91B est; EPS $2.62 vs $2.42 est. Q4 guide is $5.8–6.3B rev and $2.45–2.79 EPS, a midpoint roughly flat with Q3 and above Q3's guide range. The open-question flag from 10/26 is resolved. [247wallst](https://247wallst.com/cards/texas-instruments-q3-2026-earnings-txn-01m5g1n6r3j45hcsgta6qbhjgw), [stockhub](https://stockhub.kr/en/insights/20261022-txn-cy26q3)
- **MMM:** adj EPS $2.50 vs $2.39; FY guide raised to $9.10–9.15 from $8.80–8.95. [insiderfinance](https://www.insiderfinance.io/news/3m-raises-2026-guidance-as-q3-profit-jumps)
- **ELV (new):** FY26 guide raised to ≥ $29.00 adj EPS and $6.5B OCF (10/21). It gets in on the beat-and-raise. Managed-care sector risk overlaps with UNH, so take **at most one of UNH/ELV** this week for sector concentration. If both clear the gate, prefer ELV (raised guidance vs UNH's maintained). [insiderfinance](https://www.insiderfinance.io/news/elevance-health-earnings-lift-2026-guidance)
- **UNH:** Q3 EPS $4.69 beat, rev $112.7B; FY guide maintained. [marketbeat](https://www.marketbeat.com/instant-alerts/price-unitedhealth-group-nyse-unh-stock-falls-17-whats-next-2026-10-26/)
- **NOC:** JPM raised its PT to $605 (Neutral, 10/26) and Baird to $675 (10/21); FY adj EPS guide raised to $29.35–29.75. [marketbeat](https://www.marketbeat.com/instant-alerts/price-northrop-grumman-nyse-noc-stock-jumps-26-after-analyst-upgrade-2026-10-26/)
- **DHR, UNP:** no fresh news found; thesis carried over from 10/26 unchanged.

**Considered, not added:** ROP (10/22 beat+raise, +9% on day) — RSI 81, stretched; watch for pullback. PH, CTAS raised guidance but no technical check yet; candidates for Fri's premarket. T (AT&T) beat-and-raise sold off; skip.

**Macro:** FOMC meets 10/27–28, decision Wed 14:00 ET. Previews lean hold, and one (IFCM) cites a hawkish bias and a September hike that the other sources don't confirm. Durable Goods and New Home Sales are today; GDP and Core PCE are Thu. This is a mega-cap earnings week, and about 25% of S&P weight reports. SPY closed 10/26 at $765.23, just below its 50d of $767.57 (RSI 47). Market tone: cautious. [Fed calendar](https://www.federalreserve.gov/newsevents/2026-october.htm), [IFCM calendar](https://www.ifcmarkets.com/ru/next-week-calendar/usdidx-economic-calendar-20-10-2026), [TheStreet](https://pro.thestreet.com/portfolio/mark-your-calendars-for-these-portfolio-earnings-dates)

**Notes for the open routine:**
1. The draft entry prices are 10/26 closes. Recompute stop, target and shares from the actual fill price, and keep the chase limits (+1.5%).
2. C1 allows at most 3 entries this week. Today is effectively the only entry day before Friday.
3. At most one of UNH/ELV.
4. Low confidence on the catalyst leg everywhere, so everything stays half size.

**Decision:** TXN, DHR, UNP, ELV, UNH, MMM queued half. NOC demoted to watch (passed — technical).

### 2026-10-26 11:15 UTC — PREMARKET — MARKET CONTEXT (recovered)

**S&P 500:** 7,623.68 close Fri, −0.4% week, −2.4% from Oct 6 record (~7,815). Below 50d (~7,702), resting on 100d (~7,605). Mega-cap tech leading weakness.

**Macro this week:** Durable Goods Tue, FOMC Wed, GDP+PCE Thu. Fed expected on hold; market watching guidance language.

### 2026-10-26 11:15 UTC — PREMARKET — NOC

**Thesis:** Q3 beat and raised full-year guidance. RSI 26 (oversold), −9% from 50d over 5 days. Defense budget stable. Swing low at $507.
**Technicals:** entry $551.44, stop $507.32 (−8%), target $639.67 (+16%), R/R 2:1. Half size = 4 shares, risk $176.
**Decision:** rejected at open 10/26 (volume gate) — was: queued half — volume gate required (1.5× 20d) on entry day

### 2026-10-26 11:15 UTC — PREMARKET — UNH

**Thesis:** Q3 beat and raised guidance. Near swing low $362. Healthcare resilient.
**Technicals:** entry $418.09, stop $384.64 (−8%), target $484.98 (+16%), R/R 2:1. Half = 5 shares, risk $167.
**Decision:** rejected at open 10/26 (volume gate) — was: queued half — volume gate required

### 2026-10-26 11:15 UTC — PREMARKET — MMM

**Thesis:** Q3 beat and raised guidance. Near 50d, industrial recovery.
**Technicals:** entry $173.46, stop $159.58 (−8%), target $201.21 (+16%), R/R 2:1. Half = 14 shares, risk $194.
**Decision:** rejected at open 10/26 (volume gate) — was: queued half — volume gate required

### 2026-10-26 11:15 UTC — PREMARKET — DHR

**Thesis:** Q3 beat and raised guidance. Life sciences recovery thesis intact.
**Technicals:** entry $230.50, stop $212.06 (−8%), target $267.38 (+16%), R/R 2:1. Half = 8 shares, risk $184.
**Decision:** rejected at open 10/26 (volume gate) — was: queued half — volume gate required

### 2026-10-26 11:15 UTC — PREMARKET — TXN

**Thesis:** Strong growth; Q4 guidance not confirmed (TI IR returned 403). Analog semiconductor demand recovering.
**Technicals:** entry $284.69, stop $261.91 (−8%), target $330.25 (+16%), R/R 2:1. Half = 6 shares, risk $137.
**Decision:** rejected at open 10/26 (volume gate) — was: queued half — volume gate required; open routine should verify Q4 guidance before entry

### 2026-10-26 11:15 UTC — PREMARKET — UNP

**Thesis:** Q3 beat. Rail volumes recovering, pricing power intact.
**Technicals:** entry $292.87, stop $269.44 (−8%), target $339.31 (+16%), R/R 2:1. Half = 6 shares, risk $141.
**Decision:** rejected at open 10/26 (volume gate) — was: queued half — volume gate required

### 2026-10-26 13:53 UTC — OPEN — EXECUTION SUMMARY

**Account:** paper, equity $100,000, cash = buying power (A4 ✅). No halt flags. Not a blackout day (FOMC is Wed). Market open.
**Result:** 0 orders placed. All 6 queued entries rejected on the premarket volume gate (≥ 1.5× 20d avg on entry day).

Method: Alpaca free data is IEX-only, so full-day consolidated volume isn't available at 09:53 ET. Compared IEX volume 09:30–09:53 ET today against the same time window over the prior 20 sessions (same feed, so the ratio holds). Mean and median shown because October earnings days skew the mean.

| Ticker | Last | Planned | Chase limit | Rel vol (mean) | Rel vol (median) | Result |
|---|---|---|---|---|---|---|
| NOC | 557.07 | 551.44 | 559.71 | 0.69× | 1.05× | rejected (volume) |
| UNH | 417.64 | 418.09 | 424.36 | 0.37× | 0.59× | rejected (volume) |
| MMM | 174.77 | 173.46 | 176.06 | 0.32× | 0.44× | rejected (volume) |
| DHR | 231.77 | 230.50 | 233.96 | 0.77× | 1.12× | rejected (volume) |
| TXN | 288.07 | 284.69 | 288.96 | 0.31× | 0.36× | rejected (volume) |
| UNP | 294.73 | 292.87 | 297.26 | 0.51× | 0.62× | rejected (volume) |

All passed don't-chase (TXN close at 0.3% below the limit). Also note C1 would have capped entries at 3/6 regardless. Watchlist stays live; FOMC Wed and GDP/PCE Thu are no-entry days, so the next entry window is Tue 10/27 or Fri 10/30.

### 2026-10-26 14:37 UTC — OPEN — SCHEDULED RE-FIRE (no-op)

Scheduled open routine fired after the 13:53 UTC run had already processed today's queue. No `decision: queued` entries remain (all 6 rejected on volume gate earlier). Alpaca confirmed: equity $100,000, 0 positions, 0 orders today. No action taken.

### 2026-10-26 20:15 UTC — EOD — RECAP

Equity $100,000.00 (flat), cash 100%, 0 positions, 0 trades today. SPY +0.71% → excess −0.71% (day and WTD). D1/D4/D5 clear; `halt_today` reset to NO; `weekly_defensive: NO`. `gh` CLI auth failed (GITHUB_TOKEN rejected), so the issue was posted via the GitHub MCP integration instead.

- 2026-10-26 20:15 UTC — Issue posted: https://github.com/shaftfx/DreamCatcher/issues/3

### 2026-10-27 05:43 UTC — EOD — OFF-SCHEDULE FIRE (no-op)

`bull-eod` fired at 01:43 ET Tue (alongside `bull-premarket`), outside its `15 21 * * 1-5` UTC schedule. Market not yet open for 10/27; Monday's EOD already ran and posted issue #3. Alpaca confirmed: equity $100,000, cash $100,000, 0 positions, 0 orders since 10/27 00:00 UTC, no 10/27 SPY bar yet. No recap issue posted (would cover a session that hasn't traded); portfolio.md unchanged; flags unchanged (`halt_today: NO`). Scheduled EOD at 21:15 UTC will do today's real recap.

### 2026-10-27 06:06 UTC — Midday — OFF-SCHEDULE FIRE (no-op)

`bull-midday` fired at 02:06 ET Tue, market closed (opens 09:30 ET). Alpaca (paper) confirmed: equity $100,000 = peak, cash $100,000, multiplier 1, 0 positions, 0 open orders. D1: no session P&L yet → `halt_today: NO`. D5: equity = peak → clear. S2/S3/S4: no positions → nothing to cut, tighten, or re-stop. No orders placed; flags unchanged. Scheduled midday at 12:30 ET will do the real check.

### 2026-10-27 06:06 UTC — EOD — OFF-SCHEDULE FIRE #2 (no-op)

`bull-eod` fired again at 02:06 ET Tue, about 25 min after the 05:43 UTC off-schedule fire. Market closed (Alpaca clock: next open 09:30 ET today). Alpaca confirmed paper mode: equity $100,000, cash $100,000, buying power $100,000, 0 positions, 0 orders since 10/27 00:00 UTC. No recap issue posted, portfolio.md and flags unchanged (`halt_today: NO`). The real EOD should run after 16:00 ET today. The schedule looks misconfigured: it has now fired twice overnight.


### 2026-10-27 06:06 UTC — WEEKLY — OFF-SCHEDULE FIRE (no-op)

`bull-weekly` fired at 02:06 ET Tue 10/27, outside its `0 22 * * 5` UTC (Fri) schedule. All five bull-* routines fired within ~4s of each other at 06:05 UTC, right after each trigger was updated around 05:45 UTC. That pattern points to a manual/batch fire, not cron. The trading week is only 1 session old: Mon 10/26 equity was flat at $100,000 and SPY was +0.71%. A review now would grade a partial week, so `weekly_review.md` was NOT overwritten, no `weekly-recap` issue was posted, and `learnings.md` is unchanged. Alpaca (paper) confirmed: equity $100,000, cash $100,000, buying_power = cash, 0 positions, 0 orders since 10/26. The scheduled Friday 10/30 22:00 UTC run will do the real review.


### 2026-10-27 06:06 UTC — OPEN — OFF-SCHEDULE FIRE (no-op)

`bull-open` fired at 02:06 ET Tue. All five Bull routines fired together at 06:05 UTC, roughly 20 minutes after their triggers were updated at 05:45 UTC. The market is closed (opens 09:30 ET). No orders were placed. A market order now would fill at the open price without the chase-limit check or the time-of-day volume gate, so the queue is left **untouched**. TXN/DHR/UNP/ELV/UNH/MMM stay `queued half` for the scheduled open. Alpaca shows equity $100,000, cash = buying power, multiplier 1, 0 positions, 0 orders. Flags unchanged.

Schedule note for the user: `bull-open` cron is `35 14 * * 1-5` UTC. That is **10:35 ET** while EDT is in effect (through Sun 11/1) and 09:35 ET after the switch to EST. Today's real open run therefore lands at 10:35 ET, one hour later than the routine's intended 09:35. The volume-gate window will be 09:30–10:35, which is still valid.

### 2026-10-27 06:06 UTC — PREMARKET — DUPLICATE FIRE (no-op)

`bull-premarket` fired again at 02:06 ET, 21 min after the 05:45 UTC premarket had already completed today's full research and watchlist refresh. Alpaca re-checked (paper): equity $100,000, cash = buying power, multiplier 1, 0 positions, 0 open orders. D5 clear, no halt flags. Today's watchlist and queued plans above stand unchanged. No new research, because overnight news is unchanged at this hour and the 05:45 run's data is still current. The open routine should act on the 05:45 entry.

### 2026-10-27 11:11 UTC — PREMARKET — SCHEDULED RUN (refresh, no changes to queue)

This is the actual scheduled premarket (07:11 ET). The 05:45 UTC run did the full research and technicals. This run re-verified them and checked overnight and morning news.

**Account (Alpaca, paper, confirmed with `paper-api`):** equity $100,000, cash = buying power, multiplier 1 (A4 ✅), status ACTIVE. 0 positions, 0 orders since 10/26. D5 clear (equity = peak). No halt flags. Today is not a blackout day (FOMC decision is Wed).

**Technicals:** Alpaca IEX snapshots show the latest trades are still the 10/26 closes (TXN 298.02, DHR 233.01, UNP 296.96, ELV 431.37, UNH 410.45, MMM 172.77, NOC 565.67, SPY 765.23), identical to the 05:45 inputs. SMA50, RSI and swing lows from that run stand, so nothing was recomputed or carried over from older entries.

**News since 05:45 UTC:**
- **CNC (Centene) Q3, 06:00 ET today:** adj EPS $0.58, revenue ~$50.6B, HBR 92.7%. FY26 adj EPS guide **raised** to > $5.20 (from > $4.80; Reuters consensus ~$4.88), and the FY HBR range lowered to 90.4–91.1%. Coverage conflicts on whether the quarter beat. The raised guide and lower cost ratio read as a **positive** sector signal for UNH/ELV. That doesn't change the at-most-one-of-UNH/ELV rule, and ELV is still preferred. HCA (07:30) and UHS (after close) also report today; check whether managed care gaps on the CNC print and confirm the move with volume before entering. [Centene IR](https://investors.centene.com/2026-10-27-CENTENE-CORPORATION-REPORTS-THIRD-QUARTER-2026-RESULTS), [KSL/Reuters](https://www.ksl.com/article/51641497/centene-lifts-annual-profit-forecast-reports-upbeat-third-quarter-results), [GuruFocus](https://www.gurufocus.com/news/9144143/centene-corp-reports-q3-loss-of-014-eps-and-revenue-of-506-billion-adjusted-eps-of-058-falls-short-of-analyst-expectations)
- **Read-throughs for the industrial names, all reporting premarket today:** UPS, ITW, PCAR, JCI, XYL, PNR and HUBB matter for UNP (rail and freight volumes, via UPS and PCAR) and MMM (ITW). Their results weren't checked at this hour because most report 07:00–08:00 ET. **Open routine:** before entering UNP or MMM, take a quick look at how UPS and ITW reacted. A sharp miss or freight-volume warning is a reason to skip. [Newsquawk calendar](https://www.newsquawk.com/headlines/newsquawk-daily-us-earnings-estimates---27th-october-2026-ko-glw-spgi-ba-stx-v)
- **Other big reporters today:** KO, BA, SPGI, PYPL, SHW, GLW and FCX premarket, then V, NXPI, STX and WM after close. None are on the watchlist. NXPI reports after close, which is an analog-semis read-through for TXN *tomorrow*, but tomorrow is an FOMC no-entry day anyway.
- **Macro:** Durable Goods (08:30), Consumer Confidence and New Home Sales (10:00) are due today, and none were out at run time. FOMC starts today, with the decision Wed at 14:00 ET. Oil is lower on hopes of a US–Iran resolution, but Brent is still near six-month highs (Business Standard). Tone is cautious.
- **Search quality:** thin. No dated 10/27 upgrade roundup or futures report was found, and Schwab's market page returned an auth error. Absence of news is **not** confirmation.

**Watchlist:** unchanged. Nothing was added or removed, and all theses are intact. PH and CTAS (from 05:45) still haven't had a technical check and can wait until Fri's premarket.

**Decision:** TXN, DHR, UNP, ELV, UNH and MMM stay `queued half` per the 05:45 plans, with the same chase limits and the 1.5× time-of-day relative-volume gate (median). C1 caps the week at 3 entries, and at most one of UNH/ELV can be taken. NOC stays watch-only. Reminder: today's open cron fires at 10:35 ET (EDT), so the volume window is 09:30–10:35.

### 2026-10-27 13:42 UTC — OPEN — EXECUTION SUMMARY

**Account (Alpaca, paper, `paper-api` confirmed):** equity $100,000, cash = buying power, multiplier 1 (A4 ✅), ACTIVE. 0 positions, 0 orders today. No halt flags; not a blackout day (FOMC decision Wed). Market open (fired 09:41 ET; cron now landing at 09:35 ET as intended, not 10:35).
**Result:** 0 orders placed. All 6 queued entries rejected on the volume gate (time-of-day relative volume ≥ 1.5×, median of prior 20 sessions).

Method: IEX 1-min bars 09:30–09:41 ET today vs the same window over the prior 20 sessions (same feed). Short window (11 min) — noisy, but no name was close.

| Ticker | Last | Chase limit | Rel vol (mean) | Rel vol (median) | Result |
|---|---|---|---|---|---|
| TXN | 302.51 | 302.49 | 0.35× | 0.44× | rejected (volume + over chase limit) |
| DHR | 230.82 | 236.51 | 0.34× | 0.57× | rejected (volume) |
| UNP | 295.60 | 301.41 | 0.14× | 0.17× | rejected (volume) |
| ELV | 431.31 | 437.84 | 0.58× | 0.77× | rejected (volume) |
| UNH | 410.60 | 416.61 | 0.57× | 1.00× | rejected (volume) |
| MMM | 172.09 | 175.36 | 0.38× | 0.79× | rejected (volume) |

Context: SPY 767.94 (rel vol 0.59× median) — broad market quiet into FOMC. UPS (101.13, 12.7× rel vol) and ITW (271.20, 47.8×) are trading heavily on their earnings prints; UNP/MMM were rejected on volume before the read-through mattered. Next entry window is Fri 10/30 (Wed FOMC, Thu GDP/PCE are no-entry days). Watchlist stays live for Fri premarket to re-queue with fresh technicals.

Observation for weekly review: two straight entry days, 12/12 rejections on the 1.5× gate, best 1.12×. In a pre-FOMC tape the gate may be structurally unreachable for large caps; worth reviewing whether 1.5× is the right threshold (user decision — not changed at runtime).

### 2026-10-27 21:16 UTC — EOD — RECAP

Equity $100,000.00 (flat), cash 100%, 0 positions, 0 orders today (all 6 queued entries rejected at open on the volume gate). SPY +0.58% on the day → excess −0.58%; WTD SPY +1.30% → excess −1.30%. D1/D4/D5 clear; `halt_today` reset to NO; `weekly_defensive: NO`. Wed (FOMC) and Thu (GDP/PCE) are no-entry days; next entry window Fri 10/30. Issue posted via GitHub MCP.

- 2026-10-27 21:16 UTC — Issue posted: https://github.com/shaftfx/DreamCatcher/issues/4

### 2026-10-28 11:24 UTC — PREMARKET — FOMC BLACKOUT (no research, no queue)

**Account (Alpaca, `paper-api` confirmed):** ACTIVE, equity $100,000 = last_equity = peak, cash = buying power, multiplier 1 (A4 ✅). 0 positions, 0 orders since 10/27 00:00 UTC. D5 clear (0.00% drawdown). Flags: `halt_today: NO`, `halt_until_human: NO`, `weekly_defensive: NO`.

**Blackout:** today (Wed 10/28) is FOMC decision day (14:00 ET) → RULES.md D3, no new entries. Per the premarket routine, Step 4 catalyst research is skipped. Thu 10/29 (GDP Q3 advance + PCE) is also a no-entry day per the week flags.

**Watchlist:** unchanged. TXN, DHR, UNP, ELV, UNH and MMM stay on the list. Each was rejected at the 10/27 open on the volume gate, which isn't a thesis break, and none has hit the 30-day removal window. NOC stays watch-only. No name has a dated catalyst within 5 trading days, so Step 6 drafts nothing. **Nothing is `decision: queued` for today's open.** The Fri 10/30 premarket must recompute SMA50/RSI/swing lows from Alpaca bars, since post-FOMC moves will make the 10/26 plans stale. It should also check the NXPI (10/27 AMC) read-through for TXN and the technicals for PH and CTAS.

**Decision:** no entries queued. The open routine should no-op today.

### 2026-10-28 13:52 UTC — OPEN — FOMC BLACKOUT (no-op)

**Account (Alpaca, paper, `paper-api` confirmed):** equity $100,000, cash = buying power, multiplier 1 (A4 ✅), ACTIVE. 0 positions, 0 open orders. D5 clear. Halt flags all NO.
**Halt check:** Wed 10/28 is FOMC decision day → RULES.md D3 blackout, no new entries. Premarket queued nothing anyway.
**Result:** 0 orders placed. Next entry window is Fri 10/30.

### 2026-10-28 21:18 UTC — EOD — RECAP

Equity $100,000.00 (flat), cash 100%, 0 positions, 0 orders today (FOMC blackout, RULES.md D3). SPY +0.34% on the day (769.70 → 772.28) → excess −0.34%; WTD SPY +1.64% → excess −1.64%. D1/D4/D5 clear; `halt_today` reset to NO; `weekly_defensive: NO`. Thu 10/29 (GDP/PCE) is a no-entry day; next entry window Fri 10/30. Issue posted via GitHub REST.

- 2026-10-28 21:19 UTC — Issue posted: https://github.com/shaftfx/DreamCatcher/issues/5

### 2026-10-29 11:18 UTC — PREMARKET — WATCHLIST REFRESH (no-entry day, nothing queued)

**Account (Alpaca, `paper-api` confirmed):** ACTIVE, equity $100,000 = last_equity = peak, cash = buying power, multiplier 1 (A4 ✅). 0 positions, 0 orders since 10/28 00:00 UTC. D5 clear (0.00% drawdown). Flags all NO.

**Day status:** Thu 10/29 has GDP Q3 advance and PCE, and the week flags (set 10/27) make it a no-entry day. This isn't a strict RULES.md D3 blackout (FOMC, CPI and NFP only), so Step 4 research was run to prepare Friday. **Nothing is queued for today's open.**

**FOMC outcome (10/28):** the Fed held at 3.75–4.00% on a **10–2 vote**. Cook and Hammack dissented, both in favor of a 25 bp **hike**. Chair Warsh called growth strong and inflation elevated, and gave no guidance for December. Futures still price a high chance of a hike on 12/9. The S&P closed +0.28% at 7,743.98. Read: hawkish hold. Today's PCE print matters for that December pricing, so a hot PCE is a reason for Friday's open to be extra strict on the volume gate. [Admiral Markets](https://admiralmarkets.com/analytics/traders-blog/warsh-press-conference-october-2026), [Star-Advertiser/AP](https://www.staradvertiser.com/2026/10/28/breaking-news/wall-street-rises-as-fed-holds-rates-steady-earnings-in-focus/), [ATFX](https://www.atfxcapital.com/en/analysis/market-news/fed-holds-rates-and-warsh-outlines-the-plan-for-fewer-rate-votes)

**Read-through for TXN, NXPI Q3 (10/27 AMC):** revenue ~$3.8B (+19% y/y), adj EPS $4.20 vs $4.12, plus a $5B buyback increase. The Q4 revenue guide is $3.75–3.95B, against ~$3.86B consensus. The guide comes from one German source (Goldesel) and isn't confirmed. The stock fell ~4.6%. Analog demand is fine, but the guide leaves little upside. TXN is demoted to watch-only on RSI anyway. [NXP 8-K](https://www.sec.gov/Archives/edgar/data/0001413447/000141344726000057/nxp3q26exhibit991.htm), [Goldesel](https://goldesel.de/aktien/news/nxp-semiconductors-nv-aktie-q3-ergebnis-ubertrifft-erwartungen-doch-ausblick-bremst)

**New: CTAS.** The 9/23 Q1 FY27 release raised the FY27 guide: revenue to $12.15–12.27B (from $12.10–12.25B) and adj EPS to $5.45–5.54 (from $5.36–5.50). That's the sixth straight beat, and Baird raised its PT to $222. Guidance **raised** is cited from the company's 8-K. The guide excludes the UniFirst deal, which is under FTC review. A blocked deal isn't a thesis break, but treat the FTC decision as an event risk. [Cintas 8-K](https://www.sec.gov/Archives/edgar/data/0000723254/000072325426000044/ex992026-8x31.htm), [247wallst](https://247wallst.com/cards/cintas-q1-2027-earnings-ctas-01m3749hmh0zfj3ea0etv3fqrx)

**Technicals:** all values come from Alpaca IEX daily bars through the 10/28 close, computed this run. Nothing is carried over from prior entries (learnings 2026-10-27). Values are in the watchlist table above. Changes since the 10/26 close:
- NOC's RSI fell from 71.6 to 63.8, so its technical leg now passes.
- TXN's RSI rose from 64.4 to 70.3, so its technical leg now fails.
- ELV slid to +1.2% over its 50d.
- SPY is 772.28 against its 50d of 767.61 (+0.6%), RSI 53.3.

**Search quality:** thin for today. I found no 10/29 futures or premarket wrap, no confirmed list of this week's mega-cap earnings dates, and no 10/28–29 upgrade roundup. Mega-cap tech reports this week, and those names stay excluded. The absence of news is **not** confirmation.

**Notes for the Fri 10/30 premarket and open:**
1. Recompute entry, stop and target from fresh bars and re-queue DHR, UNP, MMM, UNH/ELV (at most one), NOC and CTAS at half size. C1 allows at most 3 entries, so take them in table order unless the Friday premarket re-ranks them.
2. Check the PCE/GDP reaction and the mega-cap earnings reaction before queuing.
3. ELV: if it closes below its 50d (~$409.6), its technical leg fails, so drop it to watch.

**Decision:** no entries queued for today (Thu 10/29). NOC was promoted to active, CTAS was added, TXN was demoted to watch-only, and PH was rejected on the technical leg.

### 2026-10-29 13:51 UTC — OPEN — NO-ENTRY DAY (no-op)

**Account (Alpaca, paper, `paper-api` confirmed):** ACTIVE, equity $100,000 = last_equity = peak, cash = buying power, multiplier 1 (A4 ✅). 0 positions, 0 orders since 10/28. D5 clear. Halt flags all NO.
**Day status:** Thu 10/29 (GDP Q3 + PCE) is a no-entry day per the week flags, and premarket queued nothing.
**Result:** 0 orders placed. Next entry window is Fri 10/30.

### 2026-10-29 21:17 UTC — EOD — RECAP

Equity $100,000.00 (flat), cash 100%, 0 positions, 0 orders today (GDP/PCE no-entry day). SPY −0.36% on the day (772.28 → 769.49) → excess +0.36%; WTD SPY +1.27% → excess −1.27%. D1/D4/D5 clear; `halt_today` reset to NO; `weekly_defensive: NO`. Fri 10/30 is the next entry window; C1 0/3. I couldn't find a reliable post-close recap of the GDP/PCE prints, so the Fri premarket must source them itself before queuing.

- 2026-10-29 21:18 UTC — Issue posted: https://github.com/shaftfx/DreamCatcher/issues/6

### 2026-10-30 11:08 UTC — PREMARKET — WATCHLIST REFRESH + QUEUE (entry day, risk-off tape)

**Account (Alpaca, `paper-api` confirmed):** ACTIVE, equity $100,000 = last_equity = peak, cash = buying power, multiplier 1 (A4 ✅). 0 positions, 0 orders since 10/29 00:00 UTC. D5 clear (0.00% drawdown). Flags all NO. Market opens 09:30 ET.

**Day status:** Fri 10/30 is an entry day. It isn't a D3 blackout, because NFP first-Friday is 11/6.

**Macro (sourced this run):**
- **GDP Q3 advance (10/29):** +3.4% annualized (Q2 +2.2%), and the quarterly PCE price index was +2.1%. [BEA](https://www.bea.gov/news/2026/gdp-advance-estimate-3rd-quarter-2026)
- **September PCE (10/29), hot:** headline +0.5% m/m and +3.6% y/y, core +0.3% m/m and +3.1% y/y. Real spending was roughly flat (<0.1%). [BEA](https://www.bea.gov/news/2026/personal-income-and-outlays-september-2026)
- **Thursday's close:** S&P 500 −0.30% (7,720), Nasdaq −1.37%, Russell 2000 +1.0%, with NYSE breadth about 2:1 positive. GOOGL fell 12.6% on a revenue miss and AI capex burn, and semis fell 1.4%. Money rotated into health care (LLY +6.6%, MRK +3.8%), real estate and staples. CAT fell 9.3% after leaving targets unchanged. [MarketScreener/Reuters](https://www.marketscreener.com/news/wall-street-slides-as-alphabet-revenue-miss-revives-ai-capex-jitters-ce785fdadd89ff24), [Yahoo](https://finance.yahoo.com/markets/stocks/articles/stock-market-today-oct-29-134623155.html)
- **This morning:** S&P futures about −0.9% and Nasdaq-100 about −2%. AMZN is down after a Q3 miss, about −$42B FCF and a maintained $220B capex plan. INTC is down 20%+ on a weak forecast. Brent is above $117 and WTI above $103, and FXStreet cites December hike bets. XOM, CVX, ABBV and AZN report before the open, and none are on the watchlist. [CNBC](https://www.cnbc.com/2026/10/29/stock-market-today-live-updates.html), [TipRanks](https://www.tipranks.com/news/stock-futures-fall-as-amazon-earnings-disappoint-investors-oil-prices-rise), [FXStreet](https://fxstreet.com/news/dow-jones-futures-fall-as-tech-earnings-disappoint-fed-hike-bets-202610300807)
- **Read:** stagflation-flavored, risk-off at the index level, driven by mega-cap tech. Our watchlist sits on the side money is rotating *into*: every active name closed up on 10/29 while SPY fell. SPY closed at 769.49 against a 50d of 767.62 (+0.2%, RSI 50.7), so a −0.9% open puts SPY **below its 50d**.

**Event risk next week:** the US midterms are Tue 11/3. Coverage from 10/20 (247wallst) tied the Aug–Oct defense selloff (ITA −18%) to bets on a Democratic sweep. NOC has since recovered to +8% over its 50d, but the election is binary for defense and managed care. [247wallst](https://247wallst.com/investing/2026/10/20/defense-stocks-are-tumbling-as-wall-street-bets-on-a-democratic-sweep/)

**Search quality:** no 10/29–30 upgrade/downgrade roundup was found, and nothing name-specific came up for any watchlist ticker. The absence of news is **not** confirmation.

**Draft entry plans:** all half size, F+T with no dated catalyst. Entry is the 10/29 close. Stop = max(20-bar swing low, entry × 0.92), which is the 8% floor in every case. Target = entry + 2 × risk (R/R 2.0, P4 ✅). Shares = floor($2,500 / entry), which is about 50% of the P1 5% cap. Risk per trade is ≤ $199 (0.2% of equity, P3 ✅). Chase limit = entry × 1.015. The 10% trailing stop goes on at fill (S1).

| Rank | Ticker | Entry | Stop | Target | Chase limit | Shares | $ | Risk $ | decision |
|---|---|---|---|---|---|---|---|---|---|
| 1 | DHR | 236.98 | 218.02 | 274.90 | 240.53 | 10 | 2,370 | 190 | queued half |
| 2 | CTAS | 218.00 | 200.56 | 252.88 | 221.27 | 11 | 2,398 | 192 | queued half |
| 3 | ELV | 422.00 | 388.24 | 489.52 | 428.33 | 5 | 2,110 | 169 | queued half |
| 4 | MMM | 177.38 | 163.19 | 205.76 | 180.04 | 14 | 2,483 | 199 | queued half |
| 5 | UNP | 301.90 | 277.75 | 350.20 | 306.43 | 8 | 2,415 | 193 | queued half |
| 6 | NOC | 562.41 | 517.42 | 652.40 | 570.85 | 4 | 2,250 | 180 | queued half |
| alt | UNH | 410.91 | 378.04 | 476.66 | 417.07 | 6 | 2,465 | 197 | alternate to ELV only |

Ranking rationale: DHR and ELV are health care, which led Thursday's rotation. CTAS has a cited raised guide and room on RSI. MMM and UNP are near RSI 65–68 and at their 20-day highs, which leaves less room. NOC ranks last because of the election binary on Tue.

**Notes for the open routine:**
1. C1 allows at most 3 entries this week. Take the first 3 *in rank order* that clear the gate and the chase limit. At most one of ELV/UNH.
2. Recompute stop, target and shares from the actual fill. If a name gaps down, the plan still holds as long as it is above its 50d SMA; if it opens below the 50d, skip it (technical leg fails).
3. With SPY likely opening below its 50d on a hot PCE, the volume gate is strict: **1.5× median, no rounding.** Rel vol on a down-market open can be inflated by selling. Require the name to be **green on the day or above its prior close** at decision time, so the volume isn't distribution.
4. Before-open earnings from XOM, CVX, ABBV and AZN don't touch the watchlist. ABBV is a health care read-through only.

**Decision:** DHR, CTAS, ELV, MMM, UNP and NOC are `queued half`, with UNH as alternate to ELV. TXN stays watch-only (RSI 71.8). PH not added (below its 50d). Nothing was removed.

### 2026-10-30 13:40 UTC — OPEN — EXECUTION SUMMARY (3 entries)

**Boot:** Alpaca `paper-api` (O5 ✅). Equity $100,000, cash = BP, multiplier 1 (A4 ✅), 0 positions, 0 orders. Flags all NO, not a blackout. Clock open, 09:36 ET. SPY 760.0 (−1.2% vs 769.49 prior close, below its 50d).

**Re-validation:** live IEX price vs chase limit, then SMA50/RSI14/8-12-21-55 EMA recomputed from Alpaca daily bars plus the live print. Per the open routine I did **not** re-check intraday volume, and I did not apply premarket note 3's "green on the day" condition: the routine names the chase limit as the only price check at open. Overnight-news check: a web search for DHR/ELV/MMM found nothing dated 10/29–30. Perplexity returned an error and WebSearch was the fallback.

| Rank | Ticker | Live | Chase | SMA50 | RSI | EMA 8>12>21>55 | decision |
|---|---|---|---|---|---|---|---|
| 1 | DHR | 236.17 | 240.53 ✅ | 218.94 ✅ | 63.6 ✅ | intact, px > 8 ✅ | **placed** |
| 2 | CTAS | 222.18 | 221.27 ❌ | — | — | — | **rejected**: chase limit (+1.9% vs 10/29 close) |
| 3 | ELV | 424.64 | 428.33 ✅ | 410.65 ✅ | 53.6 ✅ | intact, px fractionally below 8 EMA (425.55); one soft miss, acceptable per indicators.md | **placed** |
| 4 | MMM | 177.79 | 180.04 ✅ | 168.53 ✅ | 65.5 ✅ | intact ✅ | **placed** |
| 5 | UNP | 303.99 | 306.43 | 287.46 | 69.9 | intact | **not placed**: C1 cap (3/3) reached. RSI 69.9 is at the limit anyway |
| 6 | NOC | 574.12 | 570.85 ❌ | — | 69.9 | — | **rejected**: chase limit, and C1 |
| alt | UNH | 414.34 | — | — | — | — | not used (ELV passed; one of UNH/ELV) |

**Rule gates (all ✅):** P1 positions are 2.4%/2.1%/2.5% of equity. P2 has no existing exposure. P3 risk at the 10% trail is $236/$216/$249 (≤ 0.25% each). P4 2R targets are set off the 8% initial stop. C1 is 3/3 and C2 is 3/8. C3: no existing positions. A1–A6 are clean (US large-cap equities, > $5).

**Execution:** OTO market buys with an 8% static stop, all filled 13:37:45Z: DHR 10 @ 236.01, ELV 5 @ 425.85, MMM 14 @ 177.95. Each static stop leg was cancelled (204) and replaced with a GTC 10% trailing stop (`bull-20261030-<T>-trail`). Re-queried open orders and all 3 trailing stops are live: DHR 212.41, ELV 382.65, MMM 160.16. S1/S4 satisfied, no naked positions.

**Notes for next routines:** C1 is full for the week of 10/26, and the count resets Mon 11/2. ELV is managed care going into the 11/3 midterms; position management only, there's no rule trigger to exit. Midday: apply S2 (−7%) and S3 (+15%).
