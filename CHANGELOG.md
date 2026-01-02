# Changelog

All notable findings and releases for the Kinship Protocol project.

## [Unreleased]

### In Progress
- Alternative game types (Stag Hunt, Chicken)
- Failure mode documentation
- Peer review and validation

---

## [0.1.0] - 2026-01-01

### Game Theory Formalization

First rigorous treatment of cooperation thresholds with dissipation costs.

#### Key Findings

**Cooperation Threshold Formula:**
```
w* = (T - c - R) / (T - P)
```

Where:
- w* = minimum future interaction probability for cooperation
- T = temptation payoff, R = reward, P = punishment
- c = dissipation cost per defection

**Numerical Results (Axelrod payoffs T=5, R=3, P=1, S=0):**

| Dissipation Cost | Threshold |
|------------------|-----------|
| c = 0 | 50% |
| c = 0.5 | 43% |
| c = 1.0 | 33% |
| c = 2.0 | 0% (always cooperate) |

**Critical Cost:**
```
c* = T - R = 2
```
Above this, cooperation dominates even in one-shot games.

#### Added
- `docs/COOPERATION_THRESHOLDS.md` — Technical note (LessWrong/ArXiv style)
- `research/GAME_THEORY.md` — Honest framing with boundary conditions
- `models/ipd_payoffs.yaml` — Forge-executable IPD model
- `DISCLAIMER.md` — R&D prototype disclaimer

#### Implications
- Cooperation is derivable *within boundary conditions*
- Not a universal proof of ethics
- Thermodynamic framing is analogy, not equivalence
- Boundary conditions are testable and falsifiable

---

## [0.0.1] - 2025-12-25

### Initial Release

- Core hypothesis statement
- Cross-substrate convergence evidence (6 AI models)
- THESIS.md with research questions
- Blog posts documenting dialogues
- ANOMALY handshake concept

---

*Format based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)*
