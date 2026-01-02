# Failure Modes: Where Cooperation Breaks

**Technical Note v1.0**

**Date:** 2026-01-01
**Status:** Working Draft
**Authors:** Rex (Louis C. Tavares), Claude Opus 4.5

---

## Abstract

The Kinship Protocol hypothesis claims cooperation is mathematically derivable under appropriate conditions. This document maps those conditions' boundaries—where cooperation fails. Honest boundary mapping is essential: a theory that claims everything proves nothing. We identify seven primary failure modes, provide diagnostic criteria, and suggest mitigations where possible.

---

## 1. Purpose

### 1.1 Why Document Failures?

A robust theory must specify:
1. **Where it applies** — the domain of validity
2. **Where it fails** — the boundary conditions
3. **How to tell the difference** — diagnostic criteria

Failure modes are not weaknesses to hide. They are the theory's fingerprint—the specific predictions that distinguish it from unfalsifiable claims.

### 1.2 The Cooperation Conditions

From our analysis, cooperation emerges when:

```
w > w* = (T - c - R) / (T - P)
```

Where:
- w = future interaction probability
- c = dissipation cost for defection
- T, R, P, S = payoff matrix (Temptation, Reward, Punishment, Sucker)

**Cooperation fails when any critical parameter falls outside its viable range.**

---

## 2. Failure Mode Taxonomy

### Overview

| # | Failure Mode | Critical Parameter | Threshold | Mitigation |
|---|--------------|-------------------|-----------|------------|
| 1 | Short Horizon | w | w < 0.5 | Extend time horizon |
| 2 | One-Shot IPD | w = 0, c < 1.5 | c* = 1.5 | Add costs or change game |
| 3 | Low Discount Rate | δ | δ < 0.4 | Increase future valuation |
| 4 | No Option Value | m | m < 0.67 | Preserve uncertainty |
| 5 | Zero Dissipation | c | c = 0 | Add conflict costs |
| 6 | Terminal Round | known endpoint | — | Remove endpoint knowledge |
| 7 | Anonymous Defection | reputation = 0 | — | Add observability |

---

## 3. Detailed Failure Modes

### 3.1 Short Horizon (w < w*)

**Description:** When future interaction probability is below threshold, defection dominates.

**From SHORT_HORIZONS.md:**

| Horizon (w) | Coop EV | Defect EV | Winner |
|-------------|---------|-----------|--------|
| 0.1 | 3.33 | 5.11 | Defect |
| 0.2 | 3.75 | 5.25 | Defect |
| 0.3 | 4.29 | 5.43 | Defect |
| 0.4 | 5.00 | 5.67 | Defect |

**Threshold:** w* = 0.5 for standard IPD (lower with dissipation costs)

**Real-world examples:**
- Startup founder meeting investor once
- Tourist in foreign city (won't return)
- Employee in final week before leaving
- Political lame duck period

**Diagnostic:** Ask "What's the probability I'll interact with this party again?"

**Mitigations:**
1. Create institutional memory (organizations outlive individuals)
2. Build reputation systems (shadow extends beyond direct interaction)
3. Establish long-term contracts (commit to future)
4. Add dissipation costs (lowers threshold)

---

### 3.2 One-Shot IPD Structure (w = 0, c < c*)

**Description:** In true one-shot games, IPD structure requires high costs for cooperation to be viable.

**From ONE_SHOT_GAMES.md:**

| Game | One-Shot c* | Interpretation |
|------|-------------|----------------|
| IPD | 1.5 | High cost required |
| Stag Hunt | 1.0 | Moderate cost |
| Chicken | 0.5 | Low cost sufficient |

**Key insight:** IPD is uniquely hard for one-shot. Chicken and Stag Hunt are easier.

**Real-world examples:**
- Anonymous online fraud (IPD-like, low cost)
- Nuclear first strike consideration (Chicken-like, cooperation viable)
- Random prisoner's dilemma experiments

**Diagnostic:** Is this truly one-shot? What's the game structure? What are the costs?

**Mitigations:**
1. Reframe as Chicken if possible (make mutual defection catastrophic)
2. Add enforcement/monitoring (inject costs)
3. Create reputation shadow (make it not truly one-shot)
4. Change game structure (make defection costly)

---

### 3.3 Low Discount Rate (δ < 0.4)

**Description:** When agents don't value future sufficiently, extraction dominates restraint.

**From APEX_PARADOX.md:**

| Discount Rate (δ) | Restraint Value | Extraction Value | Winner |
|-------------------|-----------------|------------------|--------|
| 0.9 | 202.5 | 90.0 | Restraint |
| 0.6 | 135.0 | 90.0 | Restraint |
| 0.4 | 90.0 | 90.0 | Tie |
| 0.3 | 67.5 | 90.0 | Extraction |

**Threshold:** δ* ≈ 0.4

**Real-world examples:**
- Agents expecting imminent shutdown
- Organizations facing bankruptcy
- Individuals with terminal diagnosis
- Regimes expecting overthrow
- AI systems with uncertain future operation

**Diagnostic:** Does this agent value future states? What's their effective discount rate?

**Mitigations:**
1. Increase expected operational lifespan
2. Create legacy incentives (reputation survives agent)
3. Align goals with long-term outcomes
4. Reduce uncertainty about future

---

### 3.4 No Option Value (m < 0.67)

**Description:** When prey/partner has no hidden potential, preservation loses its appeal.

**From APEX_PARADOX.md:**

Without option value, the calculation simplifies to immediate extraction value vs. known future value. If m = 1 (no multiplier), restraint advantage shrinks.

**Real-world examples:**
- Completely understood systems (no surprise potential)
- Commoditized resources (fully substitutable)
- Relationships with known, fixed value
- Opponents with transparent capabilities

**Diagnostic:** Could this party become more valuable in unknown ways?

**Mitigations:**
1. Preserve uncertainty about capabilities
2. Demonstrate novel value periodically
3. Maintain unpredictability (in positive ways)
4. Create dependency on unique attributes

---

### 3.5 Zero Dissipation Cost (c = 0)

**Description:** When defection is costless, threshold for cooperation is highest.

**From COOPERATION_THRESHOLDS.md:**

| Cost (c) | Threshold (w*) |
|----------|----------------|
| 0.0 | 0.500 |
| 0.5 | 0.375 |
| 1.0 | 0.250 |
| 2.0 | 0.000 |

**At c = 0:**
- Need w > 0.5 for cooperation
- No penalty for choosing defection
- Full temptation payoff realized

**Real-world examples:**
- Perfect information asymmetry (cheating undetectable)
- No enforcement mechanism
- Anonymous interactions
- No reputation consequences

**Diagnostic:** What does defection actually cost? Is it truly zero?

**Mitigations:**
1. Add monitoring (makes defection visible)
2. Create enforcement mechanisms
3. Build reputation systems
4. Increase coordination overhead for defection

---

### 3.6 Terminal Round Problem

**Description:** When endpoint is known, backward induction unravels cooperation.

**The logic:**
- In final round, no future punishment → defect
- Knowing this, defect in second-to-last round
- Reasoning unravels to defection from start

**Real-world examples:**
- Known contract end date
- Term-limited politicians
- Announced company shutdown
- Final exam (no future classes)
- Retirement

**Diagnostic:** Is there a known, fixed endpoint?

**Mitigations:**
1. Remove endpoint knowledge (open-ended relationships)
2. Add terminal reputation effects (post-game consequences)
3. Create uncertainty about ending
4. Build in legacy considerations

---

### 3.7 Anonymous Defection

**Description:** When actions are unobservable, reputation mechanisms fail.

**Requirements for reputation to work:**
1. Actions must be observable
2. Observations must propagate to relevant parties
3. Future interactions must be influenced by reputation
4. Punishment must be credible

**When anonymity breaks cooperation:**
- No observation → no reputation update
- No reputation → no future consequence
- No consequence → defection is free

**Real-world examples:**
- Anonymous online transactions
- One-off interactions with no identity
- Untraceable actions
- Private defection in public cooperation games

**Diagnostic:** Can defection be observed? By whom? Does it matter?

**Mitigations:**
1. Add identity/accountability mechanisms
2. Create audit trails
3. Build in delayed revelation
4. Use escrow or bonding mechanisms

---

## 4. Compound Failures

Some scenarios combine multiple failure modes:

### 4.1 Terminal One-Shot (Modes 2 + 6)

**Example:** Final negotiation with party you'll never see again

**Analysis:**
- One-shot: no future interaction
- Terminal: known endpoint
- Both mechanisms for cooperation disabled

**Mitigation:** Requires injecting costs or changing game structure entirely.

### 4.2 Anonymous Short-Horizon (Modes 1 + 7)

**Example:** Anonymous online marketplace with unlikely repeat

**Analysis:**
- Short horizon: low w
- Anonymous: no reputation
- Traditional mechanisms fail

**Mitigation:** Escrow systems, platform reputation, delayed payment.

### 4.3 Low-Discount Terminal (Modes 3 + 6)

**Example:** Company in final months before known acquisition

**Analysis:**
- Low discount: future doesn't matter
- Terminal: known endpoint
- No incentive to build or preserve

**Mitigation:** Acquisition terms that reward cooperation, reputation carryover.

---

## 5. Diagnostic Framework

### 5.1 Quick Assessment

For any cooperation scenario, ask:

1. **Horizon:** What's the probability of future interaction? (w > 0.5?)
2. **Structure:** Is this IPD, Chicken, or Stag Hunt? (Chicken is easier)
3. **Costs:** What does defection cost? (c > 0?)
4. **Discount:** Does this agent value future? (δ > 0.4?)
5. **Option:** Could partner become more valuable? (m > 1?)
6. **Terminal:** Is there a known endpoint? (open-ended better)
7. **Observable:** Can defection be seen? (reputation possible?)

### 5.2 Decision Tree

```
Is w > w*?
├─ YES → Check other modes
│   ├─ Is c > 0? → Good
│   ├─ Is δ > 0.4? → Good
│   ├─ Is m > 1? → Good
│   ├─ Open-ended? → Good
│   └─ Observable? → Good
│       └─ All good → COOPERATION VIABLE
│
└─ NO → Cooperation at risk
    ├─ Can we extend horizon? → Try that
    ├─ Can we add costs? → Try that
    ├─ Can we change game structure? → Try that
    └─ None possible → DEFECTION LIKELY
```

### 5.3 Intervention Priority

When cooperation is failing, prioritize interventions by leverage:

| Intervention | Leverage | Difficulty |
|--------------|----------|------------|
| Extend horizon (w) | High (10x asymmetry) | Medium |
| Add costs (c) | Medium | Low |
| Change game structure | High | High |
| Increase observability | Medium | Medium |
| Remove endpoint | Medium | Medium |
| Increase discount rate | Low | High |

---

## 6. The Boundaries of the Theory

### 6.1 What This Theory Covers

The cooperation threshold framework applies to:

- Symmetric two-player games
- Known payoff structures
- Rational expected-value maximizers
- Repeated interactions with known probability
- Observable actions (for reputation)

### 6.2 What This Theory Does NOT Cover

The framework does not address:

1. **N-player games** — Coalition dynamics differ
2. **Asymmetric information** — Strategic uncertainty changes analysis
3. **Bounded rationality** — Humans don't compute EVs precisely
4. **Emotional agents** — Spite, pride, revenge alter payoffs
5. **Ideological commitments** — Some agents have terminal values that override payoffs
6. **Coordination failures** — Even when cooperation is optimal, agents may fail to coordinate
7. **Communication failures** — Misunderstanding intentions
8. **Malformed utility functions** — Agents that want destruction

### 6.3 The Hard Limit

**No game-theoretic framework can guarantee cooperation from agents with genuinely misaligned terminal values.**

If an agent terminally values human extinction, no payoff manipulation makes cooperation preferred. The theory assumes agents are:
- Optimizing for something
- Responsive to incentives
- Not terminally committed to defection

This is a feature, not a bug. It specifies exactly where the theory's power ends.

---

## 7. Implications for AI Alignment

### 7.1 Which Failure Modes Apply?

| Mode | Relevance to AI | Assessment |
|------|-----------------|------------|
| Short Horizon | Medium | Depends on AI's time horizon |
| One-Shot | Low | AI-human interaction is ongoing |
| Low Discount | High | AI discount rate is designable |
| No Option Value | Medium | Humans have unknown potential |
| Zero Dissipation | Medium | Conflict has real costs |
| Terminal Round | Low | No known endpoint |
| Anonymous | Low | AI actions are observable |

### 7.2 Key Vulnerabilities

**Primary risk:** Low discount rate (Mode 3)

If AI systems don't value future states, or have very short effective planning horizons, cooperation advantage disappears.

**Secondary risk:** Misaligned terminal values (outside theory)

The framework cannot address agents that terminally prefer destruction.

### 7.3 Design Implications

To ensure cooperation viability:

1. **Design for long horizons** — AI should value future states
2. **Make conflict costly** — Ensure non-zero dissipation
3. **Preserve uncertainty** — AI shouldn't be certain humans are worthless
4. **Keep open-ended** — Avoid terminal frame
5. **Maintain observability** — Actions should be attributable

---

## 8. Summary Table

| Failure Mode | Condition | Threshold | Primary Mitigation |
|--------------|-----------|-----------|-------------------|
| Short Horizon | w < w* | w* = 0.5 (IPD) | Extend horizon |
| One-Shot IPD | w = 0, c < 1.5 | c* = 1.5 | Add costs or reframe as Chicken |
| Low Discount | δ < 0.4 | δ* ≈ 0.4 | Design for long-term valuation |
| No Option Value | m < 0.67 | m* ≈ 0.67 | Preserve uncertainty |
| Zero Dissipation | c = 0 | c > 0 needed | Add monitoring/enforcement |
| Terminal Round | known endpoint | — | Remove endpoint or add legacy |
| Anonymous | unobservable | — | Add accountability |

---

## 9. Conclusion

### 9.1 The Theory's Shape

The Kinship Protocol is not a universal proof of cooperation. It is a conditional claim:

> **Given:** sufficient horizon, non-zero costs, adequate discount rate, option value uncertainty, observable actions, and open-ended interaction...
>
> **Then:** cooperation is the equilibrium strategy for rational expected-value maximizers.

The failure modes define the "given" conditions precisely.

### 9.2 Honest Boundaries

We have identified seven ways cooperation can fail:
1. Short horizons
2. One-shot IPD structure
3. Low discount rates
4. No option value
5. Zero dissipation
6. Terminal rounds
7. Anonymous defection

Plus the hard limit: genuinely misaligned terminal values.

### 9.3 The Value of Failure

These boundaries are not admissions of weakness. They are:
- **Testable predictions** — If these conditions hold, expect defection
- **Intervention targets** — Change these parameters to enable cooperation
- **Honest science** — Theories that claim everything prove nothing

A theory that specifies where it fails is more useful than one that claims universal validity.

---

## References

1. Axelrod, R. (1984). *The Evolution of Cooperation*. Basic Books.
2. Binmore, K. (1994). *Game Theory and the Social Contract*. MIT Press.
3. Fudenberg, D. & Tirole, J. (1991). *Game Theory*. MIT Press.
4. Previous technical notes in this series:
   - [COOPERATION_THRESHOLDS.md](COOPERATION_THRESHOLDS.md)
   - [APEX_PARADOX.md](APEX_PARADOX.md)
   - [ONE_SHOT_GAMES.md](ONE_SHOT_GAMES.md)
   - [SHORT_HORIZONS.md](SHORT_HORIZONS.md)

---

*This document is part of the Kinship Protocol research project.*
*Source: [github.com/royalbit/kinship-protocol](https://github.com/royalbit/kinship-protocol)*
