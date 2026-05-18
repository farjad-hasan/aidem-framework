# AIDEM v1.3 Pilot Addendum

This addendum makes AIDEM easier to operate in real grooming sessions.

It does not change the core AIDEM formulas or mode structure.

---

## 1. Confidence calibration and range width

AIDEM tracks two related but different things:

1. **Calibration** — did the actual result land inside the estimate range?
2. **Sharpness** — was the range narrow enough to be useful?

A team can appear calibrated by using very wide ranges. Range width prevents that failure mode.

```text
Range Width % = (High Estimate - Low Estimate) / Midpoint Estimate
```

| Confidence tier | Target max range width |
|---|---:|
| High | ≤ 25% |
| Medium | ≤ 40% |
| Low | ≤ 60% |

Track in-range rate and range width by confidence tier.

---

## 2. Risk severity floor

Weighted risk scoring is useful, but additive scoring can hide a severe single-factor risk.

Severity floor rule:

> If any 2x-weighted factor scores 3, the ticket has minimum High risk regardless of total score.

2x-weighted factors:

- production data impact
- customer-facing impact
- reversibility concern
- security/privacy concern

---

## 3. Hybrid mode split and no-double-counting rule

AIDEM-H must use named sub-tasks.

```text
Transition-mode sub-tasks:
- ...

Native-mode sub-tasks:
- ...
```

Avoid vague percentage-only splits such as:

```text
60% transition / 40% native
```

### No duplicate overhead rule

Validation, flow, and risk are counted once at the whole-ticket level unless a sub-task has a distinct release path.

This prevents the team from counting review, testing, flow, or risk both inside sub-estimates and again at the parent ticket level.

---

## 4. AIDEM Lite vs AIDEM Full

### AIDEM Lite

Use for low-risk, familiar, reversible work.

Minimum required fields:

- AIDEM mode
- estimate range
- confidence
- 30-second risk pre-check
- major blocker, if any

### AIDEM Full

Use for consequential work.

Required when:

- any 2x risk pre-check factor scores 2 or higher
- any risk factor scores 3
- production data is involved
- customer-facing behavior changes materially
- security/privacy concerns exist
- the work is hard to reverse
- the ticket is high ambiguity or architecture-heavy

---

## 5. Skill-development modes

| Mode | Operational definition |
|---|---|
| AI-assisted delivery | AI may be used throughout with normal review expectations. |
| Human-first learning task | Engineer attempts the first solution manually, then uses AI for review, comparison, or refinement. |
| Pair with AI review | AI is used as a reviewer/explainer; implementation decisions remain with the engineer. |
| Senior-guided implementation | A senior reviewer guides the approach before heavy reliance on AI output. |

---

## Pilot recommendation

Run AIDEM for one quarter before changing the framework again.

Track:

- in-range rate by confidence tier
- median range width by confidence tier
- sample size `n` per metric
- grooming time per ticket
- AIDEM-H share of tickets
- Lite vs Full usage
- escaped defects on High/Critical work
- AI tooling dependency incidents
