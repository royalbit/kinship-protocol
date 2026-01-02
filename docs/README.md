# Technical Documentation

Research notes and analysis for the Kinship Protocol project.

## Index

### Cooperation Thresholds
**[COOPERATION_THRESHOLDS.md](COOPERATION_THRESHOLDS.md)**

Closed-form expressions for cooperation thresholds in iterated games with dissipation costs. Derives `w* = (T - c - R) / (T - P)` and critical cost `c* = T - R`. Extended to Stag Hunt and Chicken games in v1.1.

**Key result:** Cooperation threshold decreases monotonically with dissipation cost.

---

### The Apex Paradox
**[APEX_PARADOX.md](APEX_PARADOX.md)**

Why power doesn't imply extraction. Models predator-prey dynamics with option value to explain apex predator restraint. Shows restraint beats maximum extraction by 125% under base conditions.

**Key result:** Power asymmetry doesn't predict defection. Discount rate and option value matter more.

---

### One-Shot Games
**[ONE_SHOT_GAMES.md](ONE_SHOT_GAMES.md)**

Cooperation without a future. Analyzes when one-shot games (w=0) can support cooperation. Finds IPD is 15x harder than iterated, while Chicken and Stag Hunt have identical thresholds.

**Key result:** Game structure matters more than iteration. Frame existential scenarios as Chicken, not IPD.

---

### Short Horizons
**[SHORT_HORIZONS.md](SHORT_HORIZONS.md)**

The shadow of the future. Maps cooperation dynamics as time horizons shorten. Finds the cooperation advantage at long horizons is 10x larger than defection advantage at short horizons.

**Key result:** Horizon extension is high leverage. Any intervention that extends time horizons disproportionately favors cooperation.

---

### Failure Modes
**[FAILURE_MODES.md](FAILURE_MODES.md)**

Where cooperation breaks. Comprehensive taxonomy of seven failure modes with diagnostic criteria and mitigations. Synthesizes boundary conditions from all previous work.

**Key result:** The theory specifies where it fails—short horizons, one-shot IPD, low discount, no option value, zero costs, terminal rounds, anonymity.

---

### Edge Cases
**[EDGE_CASES.md](EDGE_CASES.md)**

Model validation across 18 edge cases. Tests extreme values, boundary conditions, degenerate games, and numerical stability.

**Key result:** All 18 tests pass. Models are robust across the parameter space.

---

## Quick Reference

| Document | Topic | Key Finding |
|----------|-------|-------------|
| COOPERATION_THRESHOLDS | IPD + multi-game thresholds | `c* = T - R` makes cooperation dominant |
| APEX_PARADOX | Asymmetric power dynamics | Restraint > extraction under uncertainty |
| ONE_SHOT_GAMES | One-shot viability | Chicken enables one-shot cooperation |
| SHORT_HORIZONS | Time horizon dynamics | Long horizons 10x more valuable for cooperation |
| FAILURE_MODES | Boundary conditions | 7 failure modes with diagnostics and mitigations |
| EDGE_CASES | Model validation | 18/18 tests pass, models robust |

## Related

- [models/README.md](../models/README.md) — Forge model quick reference
- [research/GAME_THEORY.md](../research/GAME_THEORY.md) — Theoretical framework
- [research/THESIS.md](../research/THESIS.md) — Core hypothesis
