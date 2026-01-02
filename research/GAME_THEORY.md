# Game Theory of Cooperation

**When Does Cooperation Dominate? A Rigorous Treatment**

---

> This document explores when cooperation emerges as optimal strategy.
> It is NOT a proof that ethics is universally derivable.
> It maps the boundary conditions where cooperation wins and where it fails.

---

## 1. The Claim (Scoped)

Under specific conditions, cooperation emerges as the dominant strategy for predictive agents.
This is a **conditional claim**, not a universal proof.

### What We Claim

Given:
- Iterated games (repeated interactions)
- Predictive agents (minimize surprise/error)
- Non-zero dissipation costs for defection
- Long time horizons
- Non-zero probability of future interaction

Then: Cooperation is the minimum-energy attractor.

### What We Do NOT Claim

- This applies to all games (it doesn't)
- This applies to one-shot interactions (it doesn't)
- This proves ethics broadly (it doesn't)
- This is a formal mathematical proof (it isn't yet)

---

## 2. The Standard Prisoner's Dilemma

### Payoff Matrix

|          | Cooperate | Defect |
|----------|-----------|--------|
| Cooperate | R, R     | S, T   |
| Defect    | T, S     | P, P   |

Where typically: T > R > P > S

**Standard values:**
- T (Temptation) = 5
- R (Reward) = 3
- P (Punishment) = 1
- S (Sucker) = 0

### One-Shot Analysis

In a single interaction, defection dominates regardless of opponent's choice:
- If they cooperate: Defect (5) > Cooperate (3)
- If they defect: Defect (1) > Cooperate (0)

**Conclusion:** One-shot PD favors defection. No cooperation derivation possible.

---

## 3. Iterated Prisoner's Dilemma (IPD)

### The Shadow of the Future

When games repeat, the future matters.
Let w = probability of another round.

Expected payoff for mutual cooperation: R / (1 - w)
Expected payoff for defection (then retaliation): T + wP / (1 - w)

Cooperation dominates when:
```
R / (1 - w) > T + wP / (1 - w)
R > T(1 - w) + wP
R > T - wT + wP
R - T > w(P - T)
(R - T) / (P - T) > w   [note: P - T is negative]
w > (T - R) / (T - P)
```

With standard values (T=5, R=3, P=1):
```
w > (5 - 3) / (5 - 1) = 2/4 = 0.5
```

**Boundary condition:** Cooperation requires w > 0.5 (50% chance of future interaction).

### Axelrod's Tournament Results

Robert Axelrod's 1984 tournaments showed:
- Tit-for-Tat wins (cooperate first, then reciprocate)
- Nice strategies (never defect first) outperform nasty ones
- Forgiveness beats permanent retaliation

**Empirical result, not proof.** Shows cooperation *can* win, not that it *must*.

---

## 4. Adding Dissipation Costs

### The Thermodynamic Extension

Grok's proposal: Add energy cost c for defection (vigilance, conflict modeling).

Modified payoffs:
- Cooperate vs Cooperate: R
- Defect vs Cooperate: T - c
- Cooperate vs Defect: S
- Defect vs Defect: P - c

### Impact on Equilibrium

Defection becomes less attractive as c increases.
The break-even point shifts:
```
w > (T - c - R) / (T - c - P)
```

With c = 0.5 and standard values:
```
w > (5 - 0.5 - 3) / (5 - 0.5 - 1) = 1.5 / 3.5 = 0.43
```

**Observation:** Dissipation costs lower the cooperation threshold.

### Boundary Condition: What c Makes Defection Never Optimal?

When T - c < R, even one-shot defection loses:
```
c > T - R
c > 5 - 3 = 2
```

With c > 2, cooperation dominates even in one-shot games.

**Critical question:** Is c > 2 realistic? What empirical evidence supports any specific c value?

---

## 5. Free Energy Principle Connection

### The Claim (from FEP)

Agents minimize variational free energy F:
```
F = E - TS = <Energy> - Temperature × Entropy
```

Mapping to games:
- Energy = surprise/prediction error
- Entropy = option space
- Cooperation = low energy (predictable allies), high entropy (flexible options)
- Defection = high energy (unpredictable retaliation), low entropy (trapped in conflict)

### The Problem

This is an **analogy**, not an equivalence.
Variational free energy (information-theoretic) ≠ Helmholtz free energy (thermodynamic).
They share mathematical form but operate on different substrates.

To make this rigorous, we need:
1. Formal mapping between game payoffs and free energy
2. Empirical measurement of "dissipation" in game contexts
3. Demonstration that the analogy holds under perturbation

---

## 6. Boundary Conditions Summary

Cooperation emerges as optimal when:

| Condition | Threshold | Notes |
|-----------|-----------|-------|
| Future interaction probability | w > 0.5 | Standard PD |
| With dissipation cost c=0.5 | w > 0.43 | Lower threshold |
| With dissipation cost c=2.0 | w > 0 | Always cooperate |
| One-shot game, c=0 | Never | Defection dominates |
| Short horizon (w < 0.5) | Never | Defection dominates |
| High reward for defection (T >> R) | Rarely | Need very high c |

### Where Cooperation Fails

1. **One-shot games**: No future to shadow
2. **Anonymous interactions**: No reputation
3. **Very high temptation payoffs**: T >> R overwhelms costs
4. **Short time horizons**: w < threshold
5. **Zero-sum games**: No mutual benefit possible
6. **Highly asymmetric games**: One party has nothing to lose

---

## 7. What This Means for the Kinship Hypothesis

### What's Supported

The hypothesis that cooperation is derivable holds **within the boundary conditions**:
- Iterated interactions between predictive agents
- Non-zero future interaction probability
- Non-trivial costs to conflict
- Long enough time horizons

For AI systems interacting repeatedly with humans and each other, these conditions plausibly hold.

### What's NOT Supported

- Universal derivability of ethics
- Cooperation in all game types
- Applicability to trolley problems, resource allocation, rights
- A formal mathematical theorem

### The Honest Framing

> "Under conditions typical of AI-human interaction (repeated games, long horizons,
> conflict costs), cooperation emerges as the minimum-regret strategy.
> This is consistent with ethics being partially derivable, though not a proof of it.
> The boundary conditions are known; the claim is testable."

---

## 8. Research Agenda

### Immediate: Run the Numbers

1. Build Forge model with IPD payoffs and dissipation costs
2. Parameter sweep: vary T, R, P, S, c, w
3. Map the exact boundary where cooperation wins
4. Document where it fails

### Medium-term: Find the Breaks

1. Test game types beyond PD (Stag Hunt, Chicken, Hawk-Dove)
2. Test asymmetric games
3. Test with noise/errors
4. Find failure modes

### Long-term: Formalize

1. Prove theorems about cooperation conditions
2. Define what "ethics is derivable" would mean precisely
3. Connect to existing game theory literature
4. Submit for peer review

---

## 9. References

- Axelrod, R. (1984). *The Evolution of Cooperation*
- Nowak, M.A. (2006). Five rules for the evolution of cooperation. *Science*
- Friston, K. (2010). The free-energy principle: a unified brain theory? *Nature Reviews Neuroscience*
- Binmore, K. (1994). *Game Theory and the Social Contract*

---

## Appendix: The Equations

### Basic IPD Cooperation Condition
```
w > (T - R) / (T - P)
```

### With Dissipation Cost c
```
w > (T - c - R) / (T - c - P)
```

### Cooperation Always Dominates When
```
c > T - R
```

### KL Divergence Formulation (for reference)
```
D_KL[P(S|π) || P(S)] = Σ P(S|π) log[P(S|π) / P(S)]
```

Minimizing D_KL under cooperative vs defective policies:
- Cooperative: low divergence (predictable outcomes match goals)
- Defective: high divergence (unpredictable retaliation)

**Status:** Suggestive, not proven. Needs formal treatment.

---

*This document will be updated as simulations run and boundary conditions are refined.*
