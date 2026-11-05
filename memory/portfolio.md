# Portfolio — current state

> Refreshed at the top of every routine. Source of truth is Alpaca; this file is a snapshot for context.

## Account

- **Mode:** paper
- **Last refresh (UTC):** 2026-11-05 21:16 (EOD routine, 16:16 ET, Alpaca close marks)
- **Cash:** $86,014.13
- **Equity:** $100,007.85 at Thu 11/5 close (last_equity $100,247.59 at Wed 11/4 close per Alpaca)
- **Peak equity:** $100,294.01 (11/5 pre-open marks; best close is $100,247.59 on 11/4)
- **Buying power:** $86,014.13 (= cash), multiplier 1× ✅ (RULES.md A4)

## Flags

- `halt_today: NO` (reset by EOD 2026-11-05)
- `halt_until_human: NO`
- `weekly_defensive: NO`

## Open positions

| Ticker | Qty | Entry | Entry date | Cost | Stop (trail 10%) | Target (2R) | Risk $ at stop | Thesis |
|---|---|---|---|---|---|---|---|---|
| DHR | 10 | 236.01 | 2026-10-30 | 2,360.10 | 214.61 (hwm 238.45) | 283.21 | 214 | Q3 beat+raise, life-sciences recovery (half size, F+T) |
| ELV | 5 | 425.85 | 2026-10-30 | 2,129.25 | 403.69 (hwm 448.54) | 511.02 | 111 | Q3 beat, FY26 guide raised ≥ $29 (half size, F+T) |
| MMM | 14 | 177.95 | 2026-10-30 | 2,491.30 | 177.21 (hwm 196.90) | 213.54 | 10 | Q3 beat, FY guide raised $9.10–9.15 (half size, F+T) |
| MRK | 16 | 148.82 | 2026-11-02 | 2,381.12 | 138.03 (hwm 153.37) | 178.58 | 173 | Q3 beat, FY26 adj EPS guide raised $2.77–2.82 (half size, F+T) |
| KO | 26 | 94.76 | 2026-11-02 | 2,463.83 | 87.65 (hwm 97.39) | 113.72 | 185 | Q3 beat, comparable EPS growth guide raised ≥11% (half size, F+T) |
| NOC | 4 | 540.06 | 2026-11-04 | 2,160.24 | 485.75 (hwm 539.72) | 648.07 | 217 | Q3 beat, uptrend above 50d; non-health-care diversifier (half size, F+T) |

Open positions: 6/8 (C2). All 6 GTC 10% trailing stops verified live on Alpaca at 21:16 UTC 11/5 (EOD); no trail moved after midday (S1/S4 ✅). "Risk $ at stop" = (entry − current trail) × qty; MMM's trail (177.21) is now $0.74/sh below entry, so it is close to breakeven-protected.

### EOD snapshot (2026-11-05 close)

| Ticker | Close | Value | Unrealized P&L | % from entry | Day chg $ | Days held | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|---|---|
| DHR | 226.34 | $2,263.40 | −$96.70 | −4.10% | −$85.90 | 4 | 214.61 (238.45) |
| ELV | 432.00 | $2,160.00 | +$30.75 | +1.44% | −$10.90 | 4 | 403.69 (448.54) |
| MMM | 187.77 | $2,628.78 | +$137.48 | +5.52% | −$86.52 | 4 | 177.21 (196.90) |
| MRK | 146.94 | $2,351.04 | −$30.08 | −1.26% | −$54.72 | 3 | 138.03 (153.37) |
| KO | 95.75 | $2,489.50 | +$25.67 | +1.04% | −$1.30 | 3 | 87.65 (97.39) |
| NOC | 525.25 | $2,101.00 | −$59.24 | −2.74% | −$0.40 | 1 | 485.75 (539.72) |

Total unrealized +$7.88. Market value $13,993.72 (14.0% of equity); cash 86.0%. Open risk from close to trails ≈ $918 (0.92%). The book fell −1.68% on its own market value while SPY fell −4.34% (AI/chip selloff, Nasdaq ~−5.5%). No position is at S2 (−7%) or S3 (+15%). DHR is the weakest at −4.10% (S2 = 219.49, 2.9 pts away).

### Midday snapshot (2026-11-05 17:42 UTC, 12:42 ET, Alpaca marks)

| Ticker | Current | Unrealized P&L | % from entry | Alpaca trail stop (hwm) |
|---|---|---|---|---|
| DHR | 228.41 | −$76.00 | −3.22% | 214.61 (238.45) |
| ELV | 429.82 | +$19.85 | +0.93% | 403.69 (448.54) |
| MMM | 189.93 | +$167.72 | +6.73% | 177.21 (196.90) |
| MRK | 149.44 | +$9.92 | +0.42% | 138.03 (153.37) |
| KO | 95.91 | +$29.83 | +1.21% | 87.65 (97.39) |
| NOC | 521.75 | −$73.26 | −3.39% | 485.75 (539.72) |

Total unrealized +$78.06. Intraday P&L vs Wed close equity ($100,247.59): −$169.56 (−0.17%), so D1 is clear. Drawdown −0.22% from peak ($100,294.01), so D5 is clear. No position is at S2 (−7%) or S3 (+15%). DHR (−3.22%) and NOC (−3.39%) are the weakest, both more than 3.5 pts from S2. All 6 GTC 10% trailing stops are live (S4 ✅). No actions taken.

### Premarket snapshot (2026-11-05 11:15 UTC, Alpaca pre-open marks)

| Ticker | Current | Unrealized P&L | % from entry | Alpaca trail stop (hwm) |
|---|---|---|---|---|
| DHR | 234.93 | −$10.80 | −0.46% | 213.05 (236.72) |
| ELV | 437.00 | +$55.75 | +2.62% | 394.17 (437.97) |
| MMM | 194.18 | +$227.22 | +9.12% | 175.29 (194.77) |
| MRK | 151.85 | +$48.48 | +2.04% | 135.36 (150.40) |
| KO | 96.67 | +$49.59 | +2.01% | 86.90 (96.56) |
| NOC | 521.01 | −$76.20 | −3.53% | 484.78 (538.65) |

Total unrealized +$294.04. All 6 GTC 10% trailing stops are live (S1/S4 ✅). None at S2 (−7%) or S3 (+15%). NOC is the weakest (−3.53%, 3.47 pts from S2). Drawdown 0.00% (new peak), so D5 is clear.

### EOD snapshot (2026-11-04 close)

| Ticker | Close | Value | Unrealized P&L | % from entry | Day chg $ | Days held | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|---|---|
| DHR | 234.93 | $2,349.30 | −$10.80 | −0.46% | +$48.20 | 3 | 213.05 (236.72) |
| ELV | 431.82 | $2,159.10 | +$29.85 | +1.40% | +$90.35 | 3 | 394.17 (437.97) |
| MMM | 193.95 | $2,715.30 | +$224.00 | +8.99% | +$236.60 | 3 | 175.29 (194.77) |
| MRK | 150.36 | $2,405.76 | +$24.64 | +1.04% | +$91.04 | 2 | 135.36 (150.40) |
| KO | 95.93 | $2,494.18 | +$30.35 | +1.23% | +$29.38 | 2 | 86.90 (96.56) |
| NOC | 525.35 | $2,101.40 | −$58.84 | −2.72% | −$58.84 (from fill) | 0 | 484.78 (538.65) |

Total unrealized +$239.20. Market value $14,225.04 (14.2% of equity); cash 85.8%. Open risk from close to trails ≈ $1,306 (1.30%). Health care (DHR/ELV/MRK) is 48.6% of deployed capital. No position at S2 (−7%) or S3 (+15%); MMM closest at +8.99%.

### EOD snapshot (2026-11-03 close)

| Ticker | Close | Value | Unrealized P&L | % from entry | Days held | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|---|
| DHR | 230.11 | $2,301.10 | −$59.00 | −2.50% | 2 | 213.05 (236.72) |
| ELV | 413.75 | $2,068.75 | −$60.50 | −2.84% | 2 | 384.09 (426.77) |
| MMM | 177.05 | $2,478.70 | −$12.60 | −0.51% | 2 | 162.10 (180.11) |
| MRK | 144.67 | $2,314.72 | −$66.40 | −2.79% | 1 | 134.46 (149.40) |
| KO | 94.80 | $2,464.80 | +$0.97 | +0.04% | 1 | 86.63 (96.26) |

Total unrealized −$197.53. Market value $11,628.07 (11.7% of equity). Open risk to stops ≈ $904 (0.91%). Open positions 5/8 (C2). All 5 GTC 10% trailing stops are live (S1/S4 ✅). Health care (DHR/ELV/MRK) is 57% of deployed capital.

### Midday snapshot (2026-11-03 17:42 UTC, 12:42 ET, Alpaca marks)

| Ticker | Current | Unrealized P&L | % from entry | Alpaca trail stop (hwm) |
|---|---|---|---|---|
| DHR | 231.31 | −$47.00 | −1.99% | 213.05 (236.72) |
| ELV | 414.43 | −$57.10 | −2.68% | 384.09 (426.77) |
| MMM | 176.57 | −$19.39 | −0.78% | 162.10 (180.11) |
| MRK | 144.56 | −$68.24 | −2.87% | 134.46 (149.40) |
| KO | 94.99 | +$5.78 | +0.24% | 86.63 (96.26) |

Total unrealized −$185.95. Intraday P&L vs Mon close equity ($99,884.46): −$70.43 (−0.07%), so D1 is clear. Drawdown −0.19% from peak, so D5 is clear. No position is at S2 (−7%) or S3 (+15%). All 5 GTC 10% trailing stops are live (S4 ✅). No actions taken.

### Open-routine snapshot (2026-11-03 13:36 UTC = 08:36 ET, pre-open marks)

| Ticker | Current | Unrealized P&L | % from entry | Alpaca trail stop (hwm) |
|---|---|---|---|
| DHR | 226.55 | −$94.60 | −4.01% | 213.05 (236.72) |
| ELV | 411.50 | −$71.75 | −3.37% | 384.09 (426.77) |
| MMM | 178.47 | +$7.28 | +0.29% | 162.10 (180.11) |
| MRK | 147.25 | −$25.12 | −1.06% | 134.46 (149.40) |
| KO | 94.82 | +$1.49 | +0.06% | 86.63 (96.26) |

Total unrealized −$182.70. Equity $99,817.28, drawdown −0.18% from peak (D5 clear). All 5 GTC 10% trailing stops are live (S1/S4 ✅). No entries today (none queued).

### Premarket snapshot (2026-11-03 11:08 UTC, Alpaca pre-open marks)

| Ticker | Current | Unrealized P&L | % from entry | Alpaca trail stop (hwm) |
|---|---|---|---|---|
| DHR | 227.97 | −$80.40 | −3.41% | 213.05 (236.72) |
| ELV | 413.36 | −$62.45 | −2.93% | 384.09 (426.77) |
| MMM | 177.50 | −$6.30 | −0.25% | 162.10 (180.11) |
| MRK | 147.53 | −$20.64 | −0.87% | 134.46 (149.40) |
| KO | 95.22 | +$11.89 | +0.48% | 86.63 (96.26) |

Total unrealized −$157.90. All 5 GTC 10% trailing stops are live (S1/S4 ✅). None are near S2 (−7%) or S3 (+15%).

### EOD snapshot (2026-11-02 close)

| Ticker | Close | Value | Unrealized P&L | % from entry | Days held | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|---|
| DHR | 227.97 | $2,279.70 | −$80.40 | −3.41% | 1 | 213.05 (236.72) |
| ELV | 413.60 | $2,068.00 | −$61.25 | −2.88% | 1 | 384.09 (426.77) |
| MMM | 178.36 | $2,497.04 | +$5.74 | +0.23% | 1 | 162.10 (180.11) |
| MRK | 148.30 | $2,372.80 | −$8.32 | −0.35% | 0 | 134.46 (149.40) |
| KO | 95.83 | $2,491.58 | +$27.75 | +1.13% | 0 | 86.63 (96.26) |

Total unrealized −$116.48. Deployed $11,709.12 (11.7% of equity). Open risk to stops ≈ $985 (0.99%). Open positions 5/8 (C2).

### Midday snapshot (2026-11-02 17:56 UTC, 12:56 ET, Alpaca marks)

| Ticker | Current | Unrealized P&L | % from entry | Alpaca trail stop (hwm) |
|---|---|---|---|---|
| DHR | 229.59 | −$64.20 | −2.72% | 213.05 (236.72) |
| ELV | 412.80 | −$65.28 | −3.07% | 384.09 (426.77) |
| MMM | 178.46 | +$7.14 | +0.29% | 162.10 (180.11) |
| MRK | 148.56 | −$4.24 | −0.18% | 134.27 (149.19) |
| KO | 95.47 | +$18.26 | +0.74% | 86.02 (95.58) |

Total unrealized −$108.32. Intraday P&L vs Fri close equity: +$8.93 (+0.01%), so D1 is clear. Drawdown −0.11% from peak, so D5 is clear. No position is at S2 (−7%) or S3 (+15%). All 5 GTC 10% trailing stops are live (S4 ✅).

### Premarket snapshot (2026-11-02 11:20 UTC, Alpaca marks)

| Ticker | Current | Unrealized P&L | % from entry | Alpaca trail stop (hwm) |
|---|---|---|---|---|
| DHR | 232.23 | −$37.80 | −1.60% | 213.05 (236.72) |
| ELV | 421.02 | −$24.15 | −1.13% | 384.09 (426.77) |
| MMM | 174.58 | −$47.18 | −1.89% | 160.91 (178.79) |

Total unrealized −$109.13. All 3 GTC trailing stops are live (S1/S4 ✅). None are near S2 (−7%) or S3 (+15%).

### EOD snapshot (2026-10-30 close)

| Ticker | Close | Value | Unrealized P&L | % from entry | Days held | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|---|
| DHR | 232.23 | $2,322.30 | −$37.80 | −1.60% | 0 | 213.05 (236.72) |
| ELV | 420.07 | $2,100.35 | −$28.90 | −1.36% | 0 | 384.09 (426.77) |
| MMM | 174.17 | $2,438.38 | −$52.92 | −2.12% | 0 | 160.91 (178.79) |

Total unrealized −$119.62. Deployed $6,861.03 (6.9% of equity). Open risk to stops ≈ $678 (0.68%). Open positions 3/8 (C2).

## Today's P&L (2026-11-05 close)

- Today open equity: $100,247.59 (Alpaca last_equity) → close equity: $100,007.85
- Daily return: −0.24% (−$239.74)
- SPY daily return: −4.34% (766.73 → 733.43, IEX)
- **Excess vs SPY: +4.10%**
- Drawdown from peak: −0.29% (vs $100,294.01; D5 threshold −10%)
- D1 daily loss cap: −0.24% > −2% → not breached

## Week to date (since Fri 10/30 close)

- Week return: +0.13% (prior Friday close equity $99,882.75 → $100,007.85)
- SPY week return: −2.95% (755.72 → 733.43)
- Excess vs SPY: +3.07%
- D4 weekly loss check: +0.13% > −5% → `weekly_defensive: NO`

## Prior day P&L (2026-11-04 close)

- Today open equity: $99,802.45 → close equity: $100,239.18
- Daily return: +0.44% (+$436.73)
- SPY daily return: +1.64% (754.38 → 766.73, IEX)
- Excess vs SPY: −1.20%
- Drawdown from peak: 0.00% (new peak; D5 threshold −10%)
- D1 daily loss cap: +0.44% > −2% → not breached

## Prior day P&L (2026-11-03 close)

- Today open equity: $99,884.46 → close equity: $99,802.45
- Daily return: −0.08% (−$82.01)
- SPY daily return: +0.31% (752.04 → 754.38, IEX)
- Excess vs SPY: −0.39%

## Prior day P&L (2026-11-02 close)

- Today open equity: $99,882.75 → close equity: $99,883.51
- Daily return: +0.00% (+$0.76)
- SPY daily return: −0.49% (755.72 → 752.04, IEX)
- Excess vs SPY: +0.49%
- Drawdown from peak: −0.12% (D5 threshold −10%)
- D1 daily loss cap: +0.00% > −2% → not breached

## Prior day P&L (2026-10-30 close)

- Today open equity: $100,000.00 → close equity: $99,880.38
- Daily return: −0.12%
- SPY daily return: −1.79% (769.49 → 755.72, IEX)
- Excess vs SPY: +1.67%
- Drawdown from peak: −0.12% (D5 threshold −10%)
- D1 daily loss cap: −0.12% > −2% → not breached

## Prior week (since Fri 10/23 close) — week closed

- Week return: −0.12% (prior Friday close equity $100,000.00)
- SPY week return: −0.54% (759.83 → 755.72)
- Excess vs SPY: +0.42%
- D4 weekly loss check: −0.12% > −5% → `weekly_defensive: NO`

## New entries this week

- **Week of 11/2:** 3 / 3 (RULES.md C1) — **full.** MRK and KO on Mon 11/2, NOC on Wed 11/4. No more entries until Mon 11/9.
- Prior week (10/26): 3/3, DHR, ELV, MMM (all 2026-10-30).
