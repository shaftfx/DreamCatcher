# Weekly Review

Overwritten by the Friday weekly routine each week. Prior reviews live in git history.

## Week of 2026-10-26 → 2026-10-30 (2026-W44)

_Written 2026-10-30 22:10 UTC by the weekly routine. Figures were checked against Alpaca: account, positions, open orders, portfolio history, and SPY IEX daily bars._

### Performance
- Starting equity: $100,000.00 (10/23 close, Alpaca `base_value`)
- Ending equity: $99,880.38 (10/30 close per EOD; $99,888.08 after hours)
- Week return: **−0.12%**
- SPY week return: **−0.54%** (759.83 → 755.72, IEX)
- **Excess vs SPY: +0.42%**
- Drawdown low this week: −0.135% ($99,864.66 intraday on Fri). Peak is still $100,000; D5 is nowhere near triggering.

### Trades
- Entries: 3 (DHR, ELV, MMM), all half size, all on Fri 10/30
- Exits: 0
- Wins / Losses: n/a (no closed trades)
- Avg R per closed trade: n/a
- Best open: ELV −$28.90 (−1.36%, −0.14R vs $213 risk to the trailing stop)
- Worst open: MMM −$52.92 (−2.12%, −0.21R vs $249 risk)

### Open positions (snapshot, 10/30 close)
| Ticker | Qty | Cost | Current | Unrl % | Days | Trail stop (hwm) |
|---|---|---|---|---|---|---|
| DHR | 10 | 236.01 | 232.23 | −1.60% | 0 | 213.05 (236.72) |
| ELV | 5 | 425.85 | 420.07 | −1.36% | 0 | 384.09 (426.77) |
| MMM | 14 | 177.95 | 174.17 | −2.12% | 0 | 160.91 (178.79) |

- Count 3/8. Deployed $6,861 (6.9% of equity), with 93% in cash. Total unrealized −$119.62. Open risk to stops is about $678 (0.68%).
- Largest by % of equity: MMM at 2.4%.

### What worked
- **The stop machinery.** Each of the three fills had its OTO static stop swapped for a GTC 10% trailing stop within the same run. Open orders were re-queried, and all three trailing stops are live on Alpaca (S1/S4).
- **Gate discipline on the calendar.** The FOMC blackout (Wed) and the GDP/PCE no-entry day (Thu) were respected. C1 stopped entries at 3/3 even though UNP still qualified.
- **The chase limit.** It rejected CTAS (+1.9%) and NOC (above its limit) on a gap. No chasing.
- **The data-quality fix from 10/27.** Every technical was recomputed from Alpaca bars and every guidance claim was cited. No bad numbers reached an order.

### What didn't
- **The excess return came from cash, not stock selection.** We were 100% cash Mon–Thu while SPY rose 1.27%, which cost us 1.27% of excess. Then Friday's −1.79% SPY drop came while we were 93% cash, which earned back 1.67%. On the one day we held stocks, the three names fell 1.4–2.1% from their fills. Thursday's "rotation into health care and industrials" didn't protect them. That's +0.42% of excess from luck and exposure, not from picking stocks.
- **Two lost entry days (10/26, 10/27) to a self-imposed 1.5× volume gate.** STRATEGY.md always said 1.0×. The user fixed this mid-week (b1fb12d, 0af95e2).
- **The entry-day volume leg was never actually measured on the three fills.** routines/open.md says premarket validated volume, but premarket runs before the session and can't measure entry-day volume. The open run skipped the check, and it also skipped the premarket's "green on the day" note. All three names were red vs their prior closes at decision time on a −1.2% SPY open. The technical leg in STRATEGY.md includes "Volume on entry day ≥ 1.0×," so that leg was taken partly on trust.
- **R/R mismatch (P4).** Targets were set at 2R off the planned 8% initial stop (entry × 1.16). S1 then replaced that stop with a 10% trailing stop. Against the stop actually live on Alpaca, R/R is **1.6:1** on all three: DHR 37.76/23.60, ELV 68.14/42.59, MMM 28.48/17.80. P4 requires ≥ 2:1. See the grade below.

### Self-grade: **C**
Excess vs SPY is positive (+0.42%), but it came from sitting in cash on a down week, not from decisions. Two of five sessions were lost to a threshold I misapplied, and the three positions all fell on day 1. No rule was breached on purpose: sizing (P1–P3), concurrency (C1–C3), the stops (S1/S4), scope (A1–A6) and the loss caps (D1–D5) were all clean. But P4 is a real problem. If R/R is measured against the 10% trailing stop RULES.md S1 requires, every entry this week was 1.6:1, below the 2:1 minimum. I'm grading it C, not F, because the rulebook itself conflicts: STRATEGY.md says to size and target off an 8% stop, while S1 forces a 10% trail. The open run followed the documented recipe. But the effect is the same as a breach, so if the user reads P4 strictly against the live stop, this week is an **F**. That's the user's call. It isn't something I should settle in my own favor.

### Strategy adjustments proposed (PROPOSALS — not applied)
1. **Fix the P4/S1 conflict.** Choose one:
   - (a) compute the target from the stop actually live on Alpaca: 2R off a 10% trail means target = entry × 1.20;
   - (b) keep the 8% static stop as the initial stop and switch to the 10% trail only after price clears entry + 1R;
   - (c) amend P4 so it's measured against the STRATEGY initial stop.
   I lean (a), because it's the simplest and the target isn't an order anyway.
2. **Give the entry-day volume check an owner.** The open routine should compute time-of-day relative volume (≥ 1.0× median, from STRATEGY.md) at decision time, or STRATEGY.md should drop the entry-day volume clause. Right now nobody checks it.
3. **Decide whether premarket "notes for open" are binding.** Premarket added an ad-hoc "green on the day" condition, and the open routine ignored it as out of scope. Either premarket stops inventing conditions that aren't in STRATEGY.md, or open honors them. I'd rather premarket stop inventing them.

### Lessons added to learnings.md
- [risk] R/R has to be computed against the stop that's actually live on the broker, not the one in the plan.
- [entry] One day of sector rotation isn't a defensive signal. The names it favored fell almost in line with SPY the next day.
- [ops] Every gate needs exactly one routine that can measure it. The entry-day volume gate had none.

### Notes for next week (2026-W45)
- **Calendar:** Mon 11/2 is an entry day (C1 resets to 0/3), with AAPL reporting after the close. Tue 11/3 is the US midterms: be cautious, especially on NOC/UNH and on adding managed care, since ELV is already held. Wed 11/4 is the post-election reaction. **Fri 11/6 is NFP, a D3 blackout.** DST ends Sun 11/1, so the UTC crons land one hour earlier in ET.
- **Open positions:** ELV is managed care going into the election binary, so management only. All three are day 0, so watch S2 (−7%) at midday.
- **Watchlist priorities:** UNP was blocked only by C1 (RSI 69.9, at the limit). CTAS and NOC were chase-limit rejects, so they need fresh entries. UNH would double up managed care with ELV, so it's deprioritized. TXN is watch-only until it pulls back. Re-validate everything from fresh bars.
