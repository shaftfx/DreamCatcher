# Portfolio — current state

> Refreshed at the top of every routine. Source of truth is Alpaca; this file is a snapshot for context.

## Account

- **Mode:** paper
- **Last refresh (UTC):** 2026-11-11 11:16 (premarket routine, 06:16 ET, Alpaca pre-open marks)
- **Pre-open equity 11/11:** $100,261.98 (last_equity $100,318.31; long MV $18,752.30). Drawdown −0.17% from peak (D5 clear)
- **Cash:** $81,509.68
- **Equity:** $100,317.01 close (today open equity = Alpaca last_equity $100,162.25; day +$154.76 / +0.15%)
- **Long market value:** $18,807.33 (18.7% deployed; cash 81.3%)
- **Peak equity:** $100,428.38 (intraday 11/5 10:15 ET per Alpaca 15-min portfolio history; best close is now $100,317.01 on 11/10). Drawdown −0.11% at the 11/10 close (D5 trigger ≤ $90,385.54)
- **Buying power:** $81,509.68 (= cash), multiplier 1× ✅ (RULES.md A4)

## Flags

- `halt_today: NO` (reset by EOD 2026-11-10)
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
| NOC | 4 | 540.06 | 2026-11-04 | 2,160.24 | 498.12 (hwm 553.47) | 648.07 | 168 | Q3 beat, uptrend above 50d; non-health-care diversifier (half size, F+T) |
| CTAS | 11 | 222.48 | 2026-11-09 | 2,447.28 | 202.98 (hwm 225.53) | 266.98 | 215 | Q1 FY27 beat, FY27 guide raised; FTC/UniFirst decision is a binary risk (half size, F+T) |
| LIN | 4 | 514.29 | 2026-11-09 | 2,057.16 | 471.16 (hwm 523.51) | 617.15 | 173 | Q3 adj EPS +9%, FY26 guide raised to $17.82–17.92; materials diversifier (half size, F+T) |

Open positions: **8/8 (C2 full)**. All 8 GTC 10% trailing stops verified live on Alpaca at 21:16 UTC 11/10 (EOD routine) (S1/S4 ✅). "Risk $ at stop" = (entry − current trail) × qty; MMM's trail (177.21) is now $0.74/sh below entry, so it is close to breakeven-protected.

### Premarket snapshot (2026-11-11 11:16 UTC, Alpaca pre-open marks)

| Ticker | Current | Unrealized P&L | % from entry | S2 (−7%) | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|
| DHR | 236.77 | +$7.61 | +0.32% | 219.49 | 214.61 (238.45) |
| ELV | 429.65 | +$19.00 | +0.89% | 396.04 | 403.69 (448.54) |
| MMM | 189.37 | +$159.88 | +6.42% | 165.49 | 177.21 (196.90) |
| MRK | 146.43 | −$38.24 | −1.61% | 138.40 | 138.03 (153.37) |
| KO | 95.84 | +$28.01 | +1.14% | 88.13 | 87.65 (97.39) |
| NOC | 548.61 | +$34.20 | +1.58% | 502.26 | 498.12 (553.47) |
| CTAS | 225.28 | +$30.80 | +1.26% | 206.91 | 202.98 (225.53) |
| LIN | 519.48 | +$20.76 | +1.01% | 478.29 | 471.16 (523.51) |

Total unrealized +$262.02. ELV/MMM/NOC/CTAS show Tuesday's close (no pre-open prints); MRK (−1.1% vs close), KO (−1.1%) and LIN (−0.4%) are softer pre-open on thin prints. All 8 GTC 10% trailing stops live (status `new`, S1/S4 ✅); no hwm moved overnight. Nothing at S2 (−7%) or S3 (+15%). Drawdown −0.17% from the $100,428.38 peak (D5 trigger ≤ $90,385.54). Wed 11/11 is not a D3 day, but **C2 is 8/8**, so no entries unless a stop fills.

### EOD snapshot (2026-11-10 close)

| Ticker | Close | Value | Unrealized P&L | % from entry | Day chg $ | Days held | S2 (−7%) | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|---|---|---|
| DHR | 236.11 | $2,361.10 | +$1.00 | +0.04% | +$9.90 | 7 | 219.49 | 214.61 (238.45) |
| ELV | 429.65 | $2,148.25 | +$19.00 | +0.89% | +$57.00 | 7 | 396.04 | 403.69 (448.54) |
| MMM | 189.37 | $2,651.18 | +$159.88 | +6.42% | +$10.36 | 7 | 165.49 | 177.21 (196.90) |
| MRK | 148.05 | $2,368.80 | −$12.32 | −0.52% | −$11.36 | 6 | 138.40 | 138.03 (153.37) |
| KO | 96.86 | $2,518.36 | +$54.53 | +2.21% | +$21.58 | 6 | 88.13 | 87.65 (97.39) |
| NOC | 548.61 | $2,194.44 | +$34.20 | +1.58% | +$38.16 | 4 | 502.26 | 498.12 (553.47) |
| CTAS | 225.28 | $2,478.08 | +$30.80 | +1.26% | +$23.32 | 1 | 206.91 | 202.98 (225.53) |
| LIN | 521.78 | $2,087.12 | +$29.96 | +1.46% | +$5.80 | 1 | 478.29 | 471.16 (523.51) |

Total unrealized +$317.05. Market value $18,807.33 (18.7% of equity); cash 81.3%. Open risk from close to trails ≈ $1,565 (1.56%). Day: account +$154.76 (+0.15%) vs SPY −0.37% / QQQ −0.58% on CPI day. The book made +$154.76 on ~$18.65k (≈ +0.83%), 7 of 8 green; ELV (+$57.00) and NOC (+$38.16) led, MRK (−$11.36) was the only loser. Nothing at S2 (−7%) or S3 (+15%); MRK (−0.52%) is the weakest, MMM (+6.42%) the strongest. All 8 GTC 10% trailing stops live (status `new`, S1/S4 ✅); NOC, CTAS and LIN hwms ratcheted again after midday. Days held counts trading days including the entry day.

### Midday snapshot (2026-11-10 17:45 UTC, 12:45 ET, Alpaca marks)

| Ticker | Current | Unrealized P&L | % from entry | S2 (−7%) | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|
| DHR | 235.39 | −$6.20 | −0.26% | 219.49 | 214.61 (238.45) |
| ELV | 424.33 | −$7.60 | −0.36% | 396.04 | 403.69 (448.54) |
| MMM | 189.15 | +$156.80 | +6.29% | 165.49 | 177.21 (196.90) |
| MRK | 146.91 | −$30.56 | −1.28% | 138.40 | 138.03 (153.37) |
| KO | 96.86 | +$54.53 | +2.21% | 88.13 | 87.65 (97.39) |
| NOC | 552.96 | +$51.58 | +2.39% | 502.26 | 497.66 (552.96) |
| CTAS | 225.22 | +$30.14 | +1.23% | 206.91 | 202.77 (225.30) |
| LIN | 523.05 | +$35.04 | +1.70% | 478.29 | 471.16 (523.51) |

Total unrealized +$283.73. Intraday P&L vs Mon close equity ($100,162.25): +$121.44 (+0.12%), so D1 is clear. Drawdown −0.14% from the $100,428.38 peak, so D5 is clear. No position is at S2 (−7%) or S3 (+15%); MRK (−1.28%) is the weakest, MMM (+6.29%) the strongest. All 8 GTC 10% trailing stops are live (status `new`, S4 ✅); NOC, CTAS and LIN hwms ratcheted since the premarket. No actions taken (CPI D3 blackout; no entries in midday regardless).

### Premarket snapshot (2026-11-10 11:09 UTC, Alpaca pre-open marks)

| Ticker | Current | Unrealized P&L | % from entry | S2 (−7%) | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|
| DHR | 234.60 | −$14.10 | −0.60% | 219.49 | 214.61 (238.45) |
| ELV | 418.25 | −$38.00 | −1.79% | 396.04 | 403.69 (448.54) |
| MMM | 188.63 | +$149.52 | +6.00% | 165.49 | 177.21 (196.90) |
| MRK | 149.50 | +$10.88 | +0.46% | 138.40 | 138.03 (153.37) |
| KO | 96.00 | +$32.17 | +1.31% | 88.13 | 87.65 (97.39) |
| NOC | 540.66 | +$2.40 | +0.11% | 502.26 | 489.53 (543.92) |
| CTAS | 223.16 | +$7.48 | +0.31% | 206.91 | 202.01 (224.46) |
| LIN | 520.71 | +$25.68 | +1.25% | 478.29 | 471.08 (523.42) |

Total unrealized +$176.03. ELV/MMM/CTAS show Monday's close (no pre-open prints). All 8 GTC 10% trailing stops live (status `new`, S1/S4 ✅); no hwm moved overnight. Nothing at S2 (−7%) or S3 (+15%). Drawdown −0.25% from the $100,428.38 peak, so D5 is clear. **Tue 11/10 is CPI → D3 blackout**, and C2 is 8/8, so no entries today.

### EOD snapshot (2026-11-09 close)

| Ticker | Close | Value | Unrealized P&L | % from entry | Day chg $ | Days held | S2 (−7%) | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|---|---|---|
| DHR | 235.12 | $2,351.20 | −$8.90 | −0.38% | +$48.70 | 6 | 219.49 | 214.61 (238.45) |
| ELV | 418.25 | $2,091.25 | −$38.00 | −1.78% | −$36.85 | 6 | 396.04 | 403.69 (448.54) |
| MMM | 188.63 | $2,640.82 | +$149.52 | +6.00% | +$48.72 | 6 | 165.49 | 177.21 (196.90) |
| MRK | 148.76 | $2,380.16 | −$0.96 | −0.04% | +$32.48 | 5 | 138.40 | 138.03 (153.37) |
| KO | 95.98 | $2,495.48 | +$31.65 | +1.29% | +$8.06 | 5 | 88.13 | 87.65 (97.39) |
| NOC | 539.07 | $2,156.28 | −$3.96 | −0.18% | +$56.24 | 3 | 502.26 | 489.53 (543.92) |
| CTAS | 223.16 | $2,454.76 | +$7.48 | +0.31% | +$7.48 (from fill) | 0 | 206.91 | 202.01 (224.46) |
| LIN | 516.38 | $2,065.52 | +$8.36 | +0.41% | +$8.36 (from fill) | 0 | 478.29 | 471.08 (523.42) |

Total unrealized +$145.19. Market value $18,635.47 (18.6% of equity); cash 81.4%. Open risk from close to trails ≈ $1,438 (1.44%). Day: account +$173.19 (+0.17%) vs SPY +2.36% / QQQ +3.42% in a broad risk-on rebound. The six names held overnight made +$157.35 (≈ +1.13% of their ~$13.9k value), half of SPY's move; ELV (−$36.85) was the only loser. Nothing at S2 (−7%) or S3 (+15%); ELV (−1.78%) is the weakest, MMM (+6.00%) the strongest. All 8 GTC 10% trailing stops live (status `new`, S1/S4 ✅); CTAS and LIN hwms ratcheted after midday.

### Midday snapshot (2026-11-09 17:42 UTC, 12:42 ET, Alpaca marks)

| Ticker | Current | Unrealized P&L | % from entry | S2 (−7%) | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|
| DHR | 232.97 | −$30.40 | −1.29% | 219.49 | 214.61 (238.45) |
| ELV | 423.42 | −$12.15 | −0.57% | 396.04 | 403.69 (448.54) |
| MMM | 188.19 | +$143.36 | +5.75% | 165.49 | 177.21 (196.90) |
| MRK | 147.53 | −$20.72 | −0.87% | 138.40 | 138.03 (153.37) |
| KO | 95.78 | +$26.32 | +1.07% | 88.13 | 87.65 (97.39) |
| NOC | 539.51 | −$2.20 | −0.10% | 502.26 | 489.53 (543.92) |
| CTAS | 222.51 | +$0.33 | +0.01% | 206.91 | 200.93 (223.26) |
| LIN | 521.46 | +$28.68 | +1.39% | 478.29 | 469.45 (521.61) |

Total unrealized +$133.22. Intraday P&L vs Fri close equity ($99,971.97): +$161.22 (+0.16%), so D1 is clear. Drawdown −0.29% from the $100,428.38 peak, so D5 is clear. No position is at S2 (−7%) or S3 (+15%); DHR (−1.29%) is the weakest, MMM (+5.75%) the strongest. All 8 GTC 10% trailing stops are live (status `new`, S4 ✅); NOC, CTAS and LIN hwms ratcheted up since the open. No actions taken.

### Open-routine snapshot (2026-11-09 14:37 UTC = 09:37 ET, Alpaca live marks)

| Ticker | Current | Unrealized P&L | % from entry | S2 (−7%) | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|
| DHR | 230.07 | −$59.40 | −2.52% | 219.49 | 214.61 (238.45) |
| ELV | 425.69 | −$0.80 | −0.04% | 396.04 | 403.69 (448.54) |
| MMM | 185.98 | +$112.42 | +4.51% | 165.49 | 177.21 (196.90) |
| MRK | 146.84 | −$31.76 | −1.33% | 138.40 | 138.03 (153.37) |
| KO | 95.36 | +$15.53 | +0.63% | 88.13 | 87.65 (97.39) |
| NOC | 526.18 | −$55.52 | −2.57% | 502.26 | 485.75 (539.72) |
| CTAS | 222.21 | −$3.02 | −0.12% | 206.91 | 199.98 (222.21) |
| LIN | 514.01 | −$1.10 | −0.05% | 478.29 | 462.52 (513.91) |

Total unrealized −$23.65. Intraday vs Fri close equity ($99,971.97): +$5.77, so D1 is clear. Drawdown −0.45% from peak, so D5 is clear. **2 entries today (CTAS, LIN)**; SPGI rejected on the volume gate; UNP not taken (C2 would exceed 8). C1 2/3, C2 8/8. All 8 GTC 10% trailing stops live (S1/S4 ✅). Sector mix: health care 3 (DHR/ELV/MRK), industrials 2 (MMM/CTAS), staples 1 (KO), defense 1 (NOC), materials 1 (LIN).

### Premarket snapshot (2026-11-09 11:13 UTC, Alpaca pre-open marks)

| Ticker | Current | Unrealized P&L | % from entry | S2 (−7%) | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|
| DHR | 230.25 | −$57.60 | −2.44% | 219.49 | 214.61 (238.45) |
| ELV | 425.62 | −$1.15 | −0.05% | 396.04 | 403.69 (448.54) |
| MMM | 186.29 | +$116.76 | +4.69% | 165.49 | 177.21 (196.90) |
| MRK | 148.99 | +$2.72 | +0.11% | 138.40 | 138.03 (153.37) |
| KO | 96.26 | +$38.93 | +1.58% | 88.13 | 87.65 (97.39) |
| NOC | 528.57 | −$45.96 | −2.13% | 502.26 | 485.75 (539.72) |

Total unrealized +$54.10. DHR/ELV show Friday's close (no pre-open prints). All 6 GTC 10% trailing stops are live (status `new`, S1/S4 ✅); no hwm moved. Nothing at S2 (−7%) or S3 (+15%). Drawdown −0.37% from the $100,428.38 peak, so D5 is clear. Mon 11/9 is an entry day (C1 0/3, C2 6/8 → max 2). **Tue 11/10 is CPI → D3 blackout.**

### EOD snapshot (2026-11-06 close)

| Ticker | Close | Value | Unrealized P&L | % from entry | Day chg $ | Days held | S2 (−7%) | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|---|---|---|
| DHR | 230.25 | $2,302.50 | −$57.60 | −2.44% | +$39.10 | 5 | 219.49 | 214.61 (238.45) |
| ELV | 425.62 | $2,128.10 | −$1.15 | −0.05% | −$31.90 | 5 | 396.04 | 403.69 (448.54) |
| MMM | 183.67 | $2,571.38 | +$80.08 | +3.21% | −$57.40 | 5 | 165.49 | 177.21 (196.90) |
| MRK | 146.77 | $2,348.32 | −$32.80 | −1.38% | −$2.72 | 4 | 138.40 | 138.03 (153.37) |
| KO | 95.69 | $2,487.94 | +$24.11 | +0.98% | −$1.04 | 4 | 88.13 | 87.65 (97.39) |
| NOC | 525.01 | $2,100.04 | −$60.20 | −2.79% | −$0.96 | 2 | 502.26 | 485.75 (539.72) |

Total unrealized −$47.56. Market value $13,938.28 (13.9% of equity); cash 86.1%. Open risk from close to trails ≈ $862 (0.86%). The book fell −$54.92 (−0.39% of its market value) while SPY rose +0.27%. MMM (−$57.40, now 6.7% off its 196.90 hwm) and ELV (−$31.90) did the damage; DHR bounced +$39.10. Nothing at S2 (−7%) or S3 (+15%). NOC (−2.79%) and DHR (−2.44%) are the weakest. All 6 GTC 10% trailing stops are live (status `new`, S1/S4 ✅); no hwm moved today.

### Midday snapshot (2026-11-06 17:42 UTC, 12:42 ET, Alpaca marks)

| Ticker | Current | Unrealized P&L | % from entry | S2 (−7%) | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|
| DHR | 228.74 | −$72.70 | −3.08% | 219.49 | 214.61 (238.45) |
| ELV | 429.53 | +$18.40 | +0.86% | 396.04 | 403.69 (448.54) |
| MMM | 186.91 | +$125.44 | +5.04% | 165.49 | 177.21 (196.90) |
| MRK | 147.00 | −$29.12 | −1.22% | 138.40 | 138.03 (153.37) |
| KO | 96.11 | +$35.03 | +1.42% | 88.13 | 87.65 (97.39) |
| NOC | 525.92 | −$56.56 | −2.62% | 502.26 | 485.75 (539.72) |

Total unrealized +$20.49. Intraday P&L vs Thu close equity ($100,007.33): +$12.87 (+0.01%), so D1 is clear. Drawdown −0.27% from peak ($100,294.01), so D5 is clear. No position is at S2 (−7%) or S3 (+15%). DHR (−3.08%) is the weakest, 3.9 pts from S2. All 6 GTC 10% trailing stops are live (status `new`, S4 ✅). No actions taken.

### Open-routine snapshot (2026-11-06 14:35 UTC = 09:35 ET, Alpaca live marks)

| Ticker | Current | Unrealized P&L | % from entry | S2 (−7%) | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|
| DHR | 225.42 | −$105.90 | −4.49% | 219.49 | 214.61 (238.45) |
| ELV | 425.84 | −$0.05 | −0.00% | 396.04 | 403.69 (448.54) |
| MMM | 184.17 | +$87.01 | +3.49% | 165.49 | 177.21 (196.90) |
| MRK | 145.51 | −$53.04 | −2.23% | 138.40 | 138.03 (153.37) |
| KO | 94.03 | −$19.05 | −0.77% | 88.13 | 87.65 (97.39) |
| NOC | 513.40 | −$106.63 | −4.94% | 502.26 | 485.75 (539.72) |

Total unrealized −$197.66. Intraday vs Thu close equity: −$205.02 (−0.21%), so D1 is clear. Drawdown −0.49% from peak, so D5 is clear. All 6 GTC 10% trailing stops are live (status `new`, S1/S4 ✅). NOC is now the closest to S2 (−4.94%, 2.06 pts away), then DHR (−4.49%). **No entries:** NFP D3 blackout and C1 3/3. Nothing queued for today.

### Premarket snapshot (2026-11-06 11:20 UTC, Alpaca pre-open marks)

| Ticker | Current | Unrealized P&L | % from entry | S2 (−7%) | Alpaca trail stop (hwm) |
|---|---|---|---|---|---|
| DHR | 226.34 | −$96.70 | −4.10% | 219.49 | 214.61 (238.45) |
| ELV | 432.00 | +$30.75 | +1.44% | 396.04 | 403.69 (448.54) |
| MMM | 185.00 | +$98.70 | +3.96% | 165.49 | 177.21 (196.90) |
| MRK | 144.80 | −$64.32 | −2.70% | 138.40 | 138.03 (153.37) |
| KO | 94.25 | −$13.33 | −0.54% | 88.13 | 87.65 (97.39) |
| NOC | 523.58 | −$65.92 | −3.05% | 502.26 | 485.75 (539.72) |

Total unrealized −$110.82. All 6 GTC 10% trailing stops are live (status `new`, S1/S4 ✅); no hwm moved overnight. Nothing at S2 (−7%) or S3 (+15%). DHR is the closest to S2 (2.9 pts away), then NOC (3.95 pts) and MRK (4.3 pts). Open risk from marks to trails ≈ $799 (0.80%). Pre-open marks for KO/MMM/MRK are ~1.5% under Thu's close on thin IEX prints; don't over-read them. Drawdown −0.40% from peak, so D5 is clear. Today is the NFP D3 blackout and C1 is 3/3, so no entries.

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

## Today's P&L (2026-11-10 close)

- Today open equity: $100,162.25 (Alpaca last_equity) → close equity: $100,317.01
- Daily return: +0.15% (+$154.76)
- SPY daily return: −0.37% (752.72 → 749.93, IEX)
- **Excess vs SPY: +0.52%**
- Drawdown from peak: −0.11% (vs $100,428.38; D5 threshold −10%)
- D1 daily loss cap: +0.15% > −2% → not breached

## Week to date (since Fri 11/6 close) as of Tue 11/10

- Week return: +0.36% (prior Friday close equity $99,952.41 → $100,317.01)
- SPY week return: +1.98% (735.40 → 749.93)
- Excess vs SPY: −1.61%
- D4 weekly loss check: +0.36% > −5% → `weekly_defensive: NO`
- Since the 11/4 close (before the 11/5 selloff): account +0.08% ($100,239.18 → $100,317.01) vs SPY −2.19% (766.73 → 749.93) → +2.27% excess over the full drop-and-rebound

## Prior day P&L (2026-11-09 close)

- Today open equity: $99,971.97 (Alpaca last_equity) → close equity: $100,145.16
- Daily return: +0.17% (+$173.19)
- SPY daily return: +2.36% (735.40 → 752.72, IEX)
- **Excess vs SPY: −2.18%**
- Drawdown from peak: −0.28% (vs $100,428.38; D5 threshold −10%)
- D1 daily loss cap: +0.17% > −2% → not breached

## Week to date as of Mon 11/9 (superseded)

- Week return: +0.19% (prior Friday close equity $99,952.41 → $100,145.16; +0.17% vs Alpaca's $99,971.97)
- SPY week return: +2.36% (735.40 → 752.72)
- Excess vs SPY: −2.16%
- D4 weekly loss check: +0.19% > −5% → `weekly_defensive: NO`
- Since the 11/4 close (before the 11/5 selloff): account −0.09% ($100,239.18 → $100,145.16) vs SPY −1.83% (766.73 → 752.72) → +1.74% excess over the full drop-and-rebound

## Prior day P&L (2026-11-06 close)

- Today open equity: $100,007.33 (Alpaca last_equity) → close equity: $99,952.41
- Daily return: −0.05% (−$54.92)
- SPY daily return: +0.27% (733.43 → 735.40, IEX)
- **Excess vs SPY: −0.32%**
- Drawdown from peak: −0.34% (vs $100,294.01; D5 threshold −10%)
- D1 daily loss cap: −0.05% > −2% → not breached

## Week (since Fri 10/30 close) — week closed

- Week return: +0.07% (prior Friday close equity $99,882.75 → $99,952.41)
- SPY week return: −2.69% (755.72 → 735.40)
- Excess vs SPY: +2.76%
- D4 weekly loss check: +0.07% > −5% → `weekly_defensive: NO`
- Prior Friday close for the 11/9 week: **$99,952.41**

## Prior day P&L (2026-11-05 close)

- Today open equity: $100,247.59 (Alpaca last_equity) → close equity: $100,007.85
- Daily return: −0.24% (−$239.74)
- SPY daily return: −4.34% (766.73 → 733.43, IEX)
- **Excess vs SPY: +4.10%**
- Drawdown from peak: −0.29% (vs $100,294.01; D5 threshold −10%)
- D1 daily loss cap: −0.24% > −2% → not breached

## Week to date as of Thu 11/5 (superseded)

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

- **Week of 11/9:** 2 / 3 — CTAS and LIN on Mon 11/9. C2 is 8/8, so no further entries until a position closes.
- Week of 11/2: 3 / 3 — MRK and KO on Mon 11/2, NOC on Wed 11/4.
- Prior week (10/26): 3/3, DHR, ELV, MMM (all 2026-10-30).
