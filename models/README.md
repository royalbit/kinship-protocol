# Mathematical Models

Game-theoretic models exploring cooperation dynamics.
Executable via [Forge](https://github.com/royalbit/forge).

## Quick Reference

| Model | Description | Key Finding | Docs |
|-------|-------------|-------------|------|
| [ipd_payoffs.yaml](ipd_payoffs.yaml) | IPD with dissipation costs | Breakeven c* = 2 | [COOPERATION_THRESHOLDS](../docs/COOPERATION_THRESHOLDS.md) |
| [axelrod_tournament.yaml](axelrod_tournament.yaml) | 5-strategy tournament sweep | Crossover at c = 0.1 | [COOPERATION_THRESHOLDS](../docs/COOPERATION_THRESHOLDS.md) |
| [stag_hunt.yaml](stag_hunt.yaml) | Stag Hunt with costs | Crossover at c = 1.0 | [COOPERATION_THRESHOLDS](../docs/COOPERATION_THRESHOLDS.md) |
| [chicken.yaml](chicken.yaml) | Chicken with costs | Crossover at c = 0.5 | [COOPERATION_THRESHOLDS](../docs/COOPERATION_THRESHOLDS.md) |
| [predator_prey.yaml](predator_prey.yaml) | Asymmetric power dynamics | Restraint +125% over extraction | [APEX_PARADOX](../docs/APEX_PARADOX.md) |
| [one_shot.yaml](one_shot.yaml) | One-shot game analysis | IPD 15x harder than iterated | [ONE_SHOT_GAMES](../docs/ONE_SHOT_GAMES.md) |
| [short_horizon.yaml](short_horizon.yaml) | Time horizon sweep | Long horizon 10x leverage | [SHORT_HORIZONS](../docs/SHORT_HORIZONS.md) |
| [edge_cases.yaml](edge_cases.yaml) | Model validation | 18/18 tests pass | [EDGE_CASES](../docs/EDGE_CASES.md) |
| [kinship_scenarios.yaml](kinship_scenarios.yaml) | Scenario comparison | Kinship +314 over chaos | — |

## Running Models

```bash
# Calculate all formulas
forge calculate models/<model>.yaml

# Example
forge calculate models/ipd_payoffs.yaml
```

## Key Results Summary

### Game Crossover Thresholds (Iterated)

| Game | Mutual Defect | Crossover c |
|------|---------------|-------------|
| IPD | 1 (moderate) | 0.1 |
| Chicken | 0 (catastrophic) | 0.5 |
| Stag Hunt | 3 (safe) | 1.0 |

### One-Shot vs Iterated

| Game | One-Shot c* | Iterated c* | Ratio |
|------|-------------|-------------|-------|
| IPD | 1.5 | 0.1 | 15x |
| Chicken | 0.5 | 0.5 | 1x |
| Stag Hunt | 1.0 | 1.0 | 1x |

### Asymmetric Power (Predator-Prey)

| Strategy | Total Value |
|----------|-------------|
| Max extraction | 90 |
| Restraint | 202.5 (+125%) |

## Documentation

Full analysis in [docs/](../docs/README.md):
- [COOPERATION_THRESHOLDS.md](../docs/COOPERATION_THRESHOLDS.md) — Threshold derivations
- [APEX_PARADOX.md](../docs/APEX_PARADOX.md) — Power asymmetry analysis
- [ONE_SHOT_GAMES.md](../docs/ONE_SHOT_GAMES.md) — One-shot viability
- [SHORT_HORIZONS.md](../docs/SHORT_HORIZONS.md) — Time horizon dynamics
- [FAILURE_MODES.md](../docs/FAILURE_MODES.md) — Boundary conditions
- [EDGE_CASES.md](../docs/EDGE_CASES.md) — Model validation

## Build Your Own

```bash
# Install Forge
pip install forge-models  # or see github.com/royalbit/forge

# Create model
cat > my_model.yaml << 'EOF'
_forge_version: 1.0.0
assumptions:
  T:
    value: 5
  threshold:
    value: null
    formula: "=(T - R) / (T - P)"
EOF

# Run
forge calculate my_model.yaml
```

Disagreement advances understanding. If your results differ, share your assumptions.
