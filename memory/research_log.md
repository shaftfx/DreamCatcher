# Research Log

Dated entries. Premarket appends new research; other routines append rejected ideas, thesis updates, and rule violations.

## Active Watchlist

_Last refresh: 2026-10-29 premarket (Thu, GDP Q3 + PCE day). Technicals recomputed from Alpaca IEX daily bars through the 10/28 close. **Today is a no-entry day per the week flags. It is not a RULES.md D3 blackout, but it was set as a cautious day by the 10/27 premarket. Nothing is `decision: queued` for today's open.** None of the names has a dated catalyst within 5 trading days, so Step 6 drafts no plans. The Fri 10/30 premarket must recompute entry, stop and target from that morning's bars and re-queue half size (fundamental + technical). Entry gate unchanged: time-of-day relative volume ≥ 1.5× (median of the prior 20 sessions). C1: 0/3 used this week. At most one of UNH/ELV._

| Ticker | Added | Thesis (1 line) | Catalyst | Catalyst Date | Status (10/28 close · SMA50 · RSI14 · 20-bar swing low) |
|---|---|---|---|---|---|
| DHR | 2026-10-26 | Q3 beat+raised, life-sciences recovery | none within 8w | — | active, F+T ✅ — 234.06 · 218.03 (+7.4%) · 62.4 · 211.20 |
| UNP | 2026-10-26 | Q3 beat, rail pricing power | none within 8w | — | active, F+T ✅ — 297.59 · 287.46 (+3.5%) · 64.3 · 268.73 |
| MMM | 2026-10-26 | Q3 beat ($2.50 vs $2.39), FY guide raised to $9.10–9.15 | none within 8w | — | active, F+T ✅ — 172.76 · 168.61 (+2.5%) · 58.6 · 159.49 |
| UNH | 2026-10-26 | Q3 beat ($4.69); FY guide *maintained* ~$20.50 | none within 8w | — | active, F+T ✅ — 407.05 · 389.29 (+4.6%) · 57.0 · 362.66 |
| ELV | 2026-10-27 | Q3 beat, FY26 adj EPS guide raised to ≥ $29.00 | none within 8w | — | active, F+T ✅ but weakening — 414.33 · 409.61 (+1.2%) · 47.2 · 376.19; −1.7% on 10/28, down 4% from 10/26. Recheck that it holds the 50d on Fri |
| NOC | 2026-10-26 | Q3 beat+raised (FY adj EPS $29.35–29.75) | none within 8w | — | **promoted from watch-only to active, F+T ✅**. Pulled back: 552.68 · 520.91 (+6.1%) · RSI 63.8 (was 71.6) · 470.54 |
| CTAS | 2026-10-29 | Q1 FY27 beat (adj EPS $1.39, +15.8%; rev +10.9%), FY27 guide raised to rev $12.15–12.27B and adj EPS $5.45–5.54 | Q2 FY27 earnings (late Dec, date unconfirmed); FTC review of the UniFirst deal (close expected by end of 2026) | ~late Dec | **new**, active, F+T ✅ — 212.78 · 203.83 (+4.4%) · 54.5 · 191.85 |
| TXN | 2026-10-26 | Q3 beat ($2.62 vs $2.42); Q4 guide $5.8–6.3B / EPS $2.45–2.79 | none within 8w | — | **demoted to watch-only**. Technical fails: 309.66 · 274.03 (+13.0%) · RSI 70.3 (>70). NXPI read-through is lukewarm. Revisit on a pullback |

_Removed: none. PH was checked and not added: 912.59 vs SMA50 960.04 (−4.9%) and RSI 41.3, so the technical leg fails. Stretched names to watch for a pullback: ROP (RSI 76.5, +12.9% vs 50d) and LMT (RSI 77.0, +16.3%)._

---

## Week flags (2026-10-26 week)

- **Tue 10/27:** Durable Goods + New Home Sales — entry day (not a blackout). FOMC meeting begins.
- **Wed 10/28:** FOMC decision 14:00 ET — no new entries
- **Thu 10/29:** GDP Q3 advance + PCE — cautious, no new entries
- **Fri 10/30:** next entry window (NFP first-Friday is 11/6, so 10/30 is not a blackout)
- **Excluded (earnings this week):** MSFT, GOOGL, AMZN, AAPL (11/2), KO, LLY, BA; also semis reporting this week (NVDA/AMD/INTC/AVGO/MRVL per TheStreet — dates unconfirmed)
- **Stretched, watch for pullback:** LMT (RSI 82.7, +17.5% vs 50d), ROP (beat+raise 10/22, RSI 81.1, +13.7% vs 50d), NOC (RSI 71.6)

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
