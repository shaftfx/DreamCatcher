# Risk Management — distilled from the course (Section 5)

> *"In trading/investing it's not about how much you make, but how much you don't lose."* — Bernard Baruch

Risk management is the single most important skill. The course frames it as the life jacket: when the inevitable losing streak comes, position sizing and stops are what keep the account alive.

---

## The math the course teaches

Portfolio = $6,000 example, 2% risk per trade, R/R = 3:1, win rate 50% over 30 trades:

- Risk per trade: 2% × $6,000 = **$120**
- Win = +3R = **+$360**
- Loss = -1R = **−$120**
- 15 wins × $360 = $5,400
- 15 losses × $120 = $1,800
- **Net: +$3,600** (60% gain) on a 50% win rate.

Even at R/R 2:1 with 50% accuracy: 15 × $240 − 15 × $120 = **+$1,800** (30% gain).

> *This is the power of risk management.* — course quote

The system makes money on a coin flip if R/R ≥ 2 and risk per trade is bounded.

---

## Bull's translation

| Course principle | Bull's rule (RULES.md) |
|---|---|
| Risk 1–2% per trade | P3 — risk per trade ≤ 1.5% of equity |
| Always use a stop loss | S1 — every entry sets 10% trailing stop |
| Aim for ≥ 2:1 R/R | P4 — R/R ≥ 2:1 required |
| Never average down on a loser | C3 — no adding to losing positions |
| Limit concurrent risk | C2 — max 8 open positions; P2 — max 15% in one ticker |
| Cap daily damage | D1 — −2% daily loss → halt |
| Cap weekly damage | D4 — −5% weekly → defensive posture |
| Survive black swans | D5 — −10% drawdown → kill-switch + human re-arm |

---

## What "managing risk" looks like in practice

1. **Compute risk before sizing.** Risk = (entry − stop) × shares. Set this BEFORE picking shares; let shares fall out of the math, not the other way around.
2. **Stops are non-negotiable.** Don't move a stop further from entry to "give it room." That's how small losses become big ones.
3. **Trailing stops > fixed stops** for swing trades. Once a trade is in profit, the trailing stop locks in some gain.
4. **R/R is computed at entry.** If you can't see a clean path to 2× the stop distance, the trade isn't worth taking.
5. **Concurrent exposure matters.** Three positions each at 5% risk can correlate and become a 15% portfolio hit on a bad day. Watch sector concentration.
6. **Drawdowns trigger smaller bets, not bigger ones.** When the equity curve dips, the dollar-risk shrinks proportionally. Don't try to "win it back" with bigger size.

---

## What the course warns against (do not do)

- "Never go for trades that have high risk and low reward, do not gamble."
- Skipping the stop because "I have a feeling."
- Adding to a losing position to lower the average cost ("averaging down").
- Risking more than 2% on a single idea, no matter how confident.
- Ignoring drawdowns and continuing as if nothing changed.

---

## How Bull self-audits

At each routine boot:
- Read current equity vs peak. If drawdown > 5%, posture cautious — half-sized entries until equity recovers.
- Check that every open position has an active stop on Alpaca. If any is missing, place one immediately or close the position (RULES.md S4).
- Check sum of open-position risk (sum of `(entry − stop) × shares` for all positions). If > 5% of equity, no new entries until something exits.

The rules are the life jacket. **Always wear the life jacket.**
