# Technical Indicators — quick reference

Distilled from the user's *Technical Analysis Mastery* course, Section 4.

Indicators are confirmations, not signals. They tell you "is the trend healthy?" and "is this overextended?" — not "buy now."

---

## RSI (Relative Strength Index, 14-period)

- Bounded 0–100. Computed from average gains vs. average losses over 14 bars.
- **>70**: overbought — be cautious about new long entries.
- **<30**: oversold — possible bounce, but in strong downtrends RSI can stay <30 for weeks.
- **40–70**: healthy uptrend zone — Bull's preferred entry window.
- **50 line**: rough trend dividing line. Above 50 = bullish bias.

### RSI Divergence
- **Regular bullish divergence**: price makes lower low, RSI makes higher low → momentum is fading on the downside, possible reversal up.
- **Regular bearish divergence**: price makes higher high, RSI makes lower high → upside losing steam, possible top.
- **Hidden bullish**: price higher low, RSI lower low → continuation up.
- **Hidden bearish**: price lower high, RSI higher high → continuation down.

Bull uses divergences as **secondary** confirmation when entering at a pullback.

---

## MACD (Moving Average Convergence Divergence)

- Default: 12 EMA − 26 EMA = MACD line; signal = 9 EMA of MACD; histogram = MACD − signal.
- **MACD crosses above signal** = bullish momentum shift.
- **MACD crosses below signal** = bearish momentum shift.
- **Zero-line cross**: MACD crossing above zero = trend confirmed bullish; below zero = bearish.
- **Histogram expansion** = trend accelerating; histogram contraction = trend losing steam.

Bull uses MACD as a **trend filter** — a long entry should have MACD above its signal line, ideally above zero.

---

## Stochastic Oscillator (14, 3, 3)

- Two lines, %K and %D, bounded 0–100.
- **>80**: overbought.
- **<20**: oversold.
- **%K crosses above %D in oversold zone**: bullish reversal signal.
- **%K crosses below %D in overbought zone**: bearish reversal.

Bull uses stochastic mainly to **avoid chasing**. If %K > 80 on a candidate, wait for a pullback before entering.

---

## 4EMA (Exponential Moving Averages — 8, 12, 21, 55)

The strategy from the user's course's section 5.1.

- All four EMAs ribboning in ascending order (8 > 12 > 21 > 55) with **price above the 8 EMA** = strong bullish trend ("the stack").
- Pullback to 8 EMA, then close back above it = pullback entry.
- Don't hold below 21 EMA — that's the trend giving up.
- For a swing entry: stack is intact, recent pullback touched 8 EMA, RSI is 40–70.

This is Bull's preferred trend-confirmation signal. If the 4EMA stack is broken, the technical leg of the entry framework fails.

---

## Parabolic SAR

- Plotted as dots above or below price. Below = uptrend. Above = downtrend.
- **Flip from below to above** = trend likely ending (sell signal in pure-PSAR systems).
- Bull uses PSAR as a **secondary trailing stop reference** — if PSAR flips above price on a held position, that's an early warning to prepare for the trailing-stop exit.

---

## How Bull combines indicators

For an entry, look for this stack of confirmations:

| Indicator | Required state |
|---|---|
| 4EMA stack | Intact (8 > 12 > 21 > 55), price above 8 EMA |
| RSI(14) | Between 40 and 70 |
| MACD | Line above signal, ideally above zero |
| Stochastic | Not above 80 |
| Volume | Day's volume ≥ 1.5× 20-day avg on entry candle |

This isn't a pixel-perfect checklist — it's the picture of a healthy, non-overextended uptrend. Two of these failing (e.g. MACD just below signal, but RSI 60 and 4EMA fine) is fine. Three+ failing means **wait**.
