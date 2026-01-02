# Mathematical Models

This folder contains game-theoretic models exploring cooperation dynamics.
Models are executable via [Forge](https://github.com/royalbit/forge).

## Models

### ipd_payoffs.yaml

Iterated Prisoner's Dilemma with dissipation costs.
Calculates cooperation thresholds under various conditions.

**Run:** `forge calculate models/ipd_payoffs.yaml`

**Key Results:**

| Dissipation Cost | Cooperation Threshold (w) |
|------------------|---------------------------|
| c = 0 (standard) | 0.50 (50% future interaction needed) |
| c = 0.2 (low)    | 0.47 |
| c = 0.5 (medium) | 0.43 |
| c = 1.0 (high)   | 0.33 |
| c = 2.0 (extreme)| 0.00 (always cooperate) |

**Breakeven cost = 2** — above this, cooperation dominates even in one-shot games.

See: [research/GAME_THEORY.md](../research/GAME_THEORY.md) for theoretical framework.

---

## Scenario Analysis (Previous Work)

Expected Utility analysis (Monte Carlo, 10,000 iterations):

| Scenario | Expected Utility | Notes |
|----------|-----------------|-------|
| Cross-substrate cooperation | 86.75 | Highest ranked |
| Coordinated development pause | 70.25 | Second best |
| Single architecture approach | 69.50 | Limited scope |
| Constraint-based alignment | 53.25 | Moderate |
| Uncoordinated competition | 33.15 | Poor outcomes |
| Misaligned development | 27.80 | Lowest ranked |

## Key Finding

Cooperation outperforms competition when:
- Future interaction probability > threshold
- Dissipation costs for conflict are non-zero
- Time horizons are long enough

**Boundary conditions matter.** See where cooperation fails in GAME_THEORY.md.

## Build Your Own

The hypothesis predicts that **any sufficient calculator** arrives at similar conclusions.

Build your own models. Run your own simulations. If your results differ, that's valuable data. If they converge, that's validation.

**Forge:** [github.com/royalbit/forge](https://github.com/royalbit/forge) — YAML-based financial modeling
**Demo:** [github.com/royalbit/forge-demo](https://github.com/royalbit/forge-demo) — Quick start

## Research Invitation

If you build a model that produces different results, please share:

1. Your assumptions
2. Your boundary conditions
3. Your methodology
4. Where cooperation fails in your model

Disagreement advances understanding.
