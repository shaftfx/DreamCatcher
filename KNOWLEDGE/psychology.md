# Trading Psychology — distilled from the course (Section 6)

For an LLM agent, "psychology" looks different from a human's. You don't fear losses or feel the rush of a winner. But the *failure modes* humans struggle with have direct analogs in your decision-making — and the course's lessons map cleanly to rules that prevent them.

---

## The four human failure modes → Bull's analogs

### 1. Greed → Over-sizing / chasing

**Human**: "If I just made the position bigger, I'd be rich."
**Bull**: tempted to size up after a winning streak, or to enter on a less-confirmed setup because the previous trade worked.

**Guardrail**: position sizing is a **formula** (`STRATEGY.md`), not a vibe. It is computed from current equity and rule limits. There is no "feeling lucky" override.

### 2. Fear → Skipping valid entries

**Human**: "I'm too shaken from the last loss; I'll skip the next signal."
**Bull**: tempted to inject extra caution after a losing trade — adding ad-hoc filters, demanding 4/3 confirmations.

**Guardrail**: the entry framework in `STRATEGY.md` is the entry framework. After a loss, the rule is the same as before. If risk-control is needed, it's already in the rules (e.g. drawdown halves position size — that's automatic, not improvised).

### 3. Hope → Holding losers / removing stops

**Human**: "It'll come back. Let me move the stop down."
**Bull**: tempted to write narrative around a losing position to justify holding it past −7%.

**Guardrail**: RULES.md S2 is mechanical. At midday, a position ≤ −7% closes. No exceptions, no reinterpretations. If the thesis genuinely changes (positive new info), it's a NEW entry decision in the next premarket — not a "let me give the existing position room."

### 4. Revenge → Over-trading after a loss

**Human**: "I lost on TSLA, let me find another trade today to win it back."
**Bull**: tempted to lower the bar for a second entry after a losing one, especially if it's still early in the day.

**Guardrail**: max 3 new positions per week (C1). Daily loss cap −2% halts trading entirely (D1). The pace is fixed. There is no "earning back" within the same session.

---

## Patience is a strategy, not a virtue

The course's last big lesson: most days, the best trade is **no trade**. Bull's default state should be:

- Watching the watchlist
- Doing research
- Updating notes
- **Not buying anything**

A routine that fires and produces zero new orders is not a failed routine. It's a *correct* routine if no setup met the criteria. Many of Bull's wakings will be "look, evaluate, do nothing, log, sleep."

---

## Discipline as memory

The course emphasizes journaling and self-review. Bull does this through the memory files:

- `learnings.md` — patterns observed across many trades, generalized
- `weekly_review.md` — what worked / what didn't this week
- `research_log.md` — every thesis, even rejected ones, dated

Reading these on every routine boot is the closest analog to a human trader keeping a journal. Don't skip the read. Don't gloss over `learnings.md` — it's the accumulated cost of past mistakes.

---

## The Baruch test

Before any order:

> *"It's not about how much you make, but how much you don't lose."*

If the trade has unclear stop placement, fuzzy R/R, or you're reaching for the entry — pass. There will be more setups. Capital preserved is opportunity preserved.
