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

### kinship_scenarios.yaml

Scenario comparison across coordination outcomes.

**Run:** `forge calculate models/kinship_scenarios.yaml`

**Key Results:**

| Scenario | Net Utility | Per Round |
|----------|-------------|-----------|
| Kinship Protocol | 578.5 | 2.89 |
| Coordination Pause | 510.0 | 2.55 |
| Multipolar Chaos | 264.0 | 1.32 |
| Unaligned ASI | 125.0 | 0.63 |

**Kinship advantage:** +314.5 over chaos, +453.5 over misalignment.

### axelrod_tournament.yaml

Parameter sweep of 5-strategy IPD tournament with dissipation costs.

**Run:** `forge calculate models/axelrod_tournament.yaml`

**Key Results:**

| Cost (c) | GrimTrigger | TitForTat | AlwaysDefect | AlwaysCooperate | AC wins? |
|----------|-------------|-----------|--------------|-----------------|----------|
| 0.0 | 2.622 | 2.445 | 2.212 | 2.112 | No |
| 0.1 | 2.582 | 2.415 | 2.112 | 2.112 | Tie |
| 0.2 | 2.542 | 2.385 | 2.012 | 2.112 | Yes |
| 0.3 | 2.502 | 2.355 | 1.912 | 2.112 | Yes |

**Crossover at c = 0.1** — AlwaysCooperate beats AlwaysDefect above this threshold.

See: [research/GAME_THEORY.md](../research/GAME_THEORY.md) for theoretical framework.

### stag_hunt.yaml

Stag Hunt game with dissipation costs. Tests cooperation dynamics when mutual defection is safe but suboptimal.

**Run:** `forge calculate models/stag_hunt.yaml`

**Key Results:**

| Cost (c) | Cooperation | Defection | Coop Wins? |
|----------|-------------|-----------|------------|
| 0.0 | 2.0 | 3.0 | No |
| 0.5 | 2.0 | 2.5 | No |
| 1.0 | 2.0 | 2.0 | Tie |
| 1.5 | 2.0 | 1.5 | Yes |

**Crossover at c = 1.0** — Higher threshold than IPD because mutual defection (hare-hare) yields safe payoff of 3.

### chicken.yaml

Chicken (Hawk-Dove) game with dissipation costs. Tests cooperation dynamics when mutual defection is catastrophic.

**Run:** `forge calculate models/chicken.yaml`

**Key Results:**

| Cost (c) | Cooperation | Defection | Coop Wins? |
|----------|-------------|-----------|------------|
| 0.00 | 2.0 | 2.5 | No |
| 0.25 | 2.0 | 2.25 | No |
| 0.50 | 2.0 | 2.0 | Tie |
| 1.00 | 2.0 | 1.5 | Yes |

**Crossover at c = 0.5** — Lower threshold than IPD because mutual defection (crash) yields catastrophic payoff of 0.

### Game Comparison

| Game | Mutual Defect Payoff | Crossover c |
|------|---------------------|-------------|
| IPD | 1.0 (moderate) | 0.1 |
| Chicken | 0.0 (catastrophic) | 0.5 |
| Stag Hunt | 3.0 (safe) | 1.0 |

**Finding:** The worse mutual defection is, the *higher* dissipation costs needed to flip to cooperation — because there's less defection to penalize.

### predator_prey.yaml

Asymmetric power dynamics model. Tests whether apex predators rationally choose restraint over maximum extraction.

**Run:** `forge calculate models/predator_prey.yaml`

**Key Results:**

| Strategy | Extraction Rate | Total Value |
|----------|-----------------|-------------|
| Maximum extraction | 100% | 90.0 |
| Sustainable harvest | 33% | 165.4 |
| Conservative | 15% | 185.6 |
| **Full restraint** | 0% | **202.5** |

**Restraint advantage: +112.5** (125% better than maximum extraction)

**Boundary conditions (when extraction wins):**

| Condition | Threshold | Interpretation |
|-----------|-----------|----------------|
| Low discount rate | δ < 0.4 | Predator doesn't value future |
| No growth | g < 0.67 | Prey declining anyway |
| No option value | m < 0.67 | Prey has no hidden potential |

**Key finding:** Power asymmetry doesn't imply defection. Option value and future discounting matter more than raw capability.

See: [docs/APEX_PARADOX.md](../docs/APEX_PARADOX.md) for full theoretical framework.

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
