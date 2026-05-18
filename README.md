# AIDEM — AI-Assisted Delivery Estimation Model

AIDEM is an open framework for estimating, grooming, and calibrating AI-assisted engineering work.

It helps teams avoid two common mistakes:

1. Treating AI as a blanket productivity discount.
2. Ignoring the review, testing, rework, flow, and risk costs that appear when AI enters the delivery path.

AIDEM is not a precision formula. It is a **grooming and calibration protocol** for engineering teams working with AI.

> AI changes engineering work. AIDEM keeps planning honest.

---

## Current version

**AIDEM v1.3 + Pilot Addendum + Dashboard Patch**

This version includes:

- AIDEM-T for teams transitioning into AI-assisted delivery
- AIDEM-N for AI-native teams using reference-class forecasting
- AIDEM-H for mixed/hybrid work
- Risk scoring with severity floor rules
- Confidence calibration and range-width tracking
- Lite vs Full grooming paths
- Model/tool versioning and drift rules
- Skill-development modes
- Remediation playbooks for flagged pilot metrics

---

## Why AIDEM exists

AI-assisted engineering has made traditional estimation harder, not easier.

Some work becomes faster:

- scaffolding
- boilerplate
- documentation
- test drafts
- refactoring with known patterns
- code search and explanation

But some work does not disappear:

- business judgment
- requirements ambiguity
- domain validation
- code review
- QA and regression testing
- integration and deployment flow
- production and data risk

AIDEM gives teams a structured way to discuss those tradeoffs before committing to delivery expectations.

---

## The three AIDEM modes

### AIDEM-T — Transition Mode

Use when the team has credible historical experience estimating similar work before AI assistance.

Formula:

```text
T_planning = [
  (T_AI_eligible × (1 - L))
  + T_nonAI
  + T_context
  + T_review
  + T_test
  + T_rework
  + T_flow
] × R
```

Where:

- `T_AI_eligible` = work AI can realistically accelerate
- `L` = AI leverage assumption
- `T_nonAI` = work AI does not meaningfully reduce
- `T_context` = time to provide context, examples, constraints, and repo understanding
- `T_review` = human review of AI-assisted output
- `T_test` = QA, regression, sandbox, or acceptance testing
- `T_rework` = fixing wrong assumptions, hallucinated logic, or missed edge cases
- `T_flow` = PR wait, handoffs, dependency coordination, and release overhead
- `R` = risk multiplier

### AIDEM-N — Native Mode

Use when AI is ambient in the team’s workflow and there is no credible “without AI” baseline.

Formula:

```text
T_planning = T_reference + T_validation + T_flow + T_risk
```

Where:

- `T_reference` = observed delivery range from similar completed AI-assisted work
- `T_validation` = review, QA, security, domain, or compliance validation
- `T_flow` = review wait, handoffs, release, and stakeholder flow
- `T_risk` = uncertainty buffer based on production, customer, reversibility, or security risk

### AIDEM-H — Hybrid Mode

Use when a ticket contains both transition-style and AI-native sub-work.

Hybrid mode must name the split explicitly:

```text
Transition-mode sub-tasks:
- ...

Native-mode sub-tasks:
- ...
```

No duplicate overhead rule:

> Validation, flow, and risk are counted once at the whole-ticket level unless a sub-task has a distinct release path.

If AIDEM-H exceeds 30–40% of tickets in a pilot, review whether teams are overusing Hybrid to avoid clearer mode selection.

---

## AIDEM Lite vs AIDEM Full

### AIDEM Lite

Use for low-risk, familiar, reversible work.

Minimum fields:

- Mode: T / N / H
- Estimate range
- Confidence level
- 30-second risk pre-check
- Major blocker, if any

### AIDEM Full

Required for:

- High or Critical risk work
- production data impact
- customer-facing changes
- irreversible changes
- security/privacy concern
- unclear architecture or discovery-heavy work
- hybrid work with unclear boundaries

Full mode includes the complete risk scorecard, confidence rationale, governance gates, model/tool metadata, and completion review.

---

## 30-second Lite/Full risk pre-check

Before choosing Lite, score the four 2x risk factors:

| Factor | Score |
|---|---:|
| Production data impact | 0–3 |
| Customer-facing impact | 0–3 |
| Reversibility concern | 0–3 |
| Security/privacy concern | 0–3 |

Rules:

- Any factor scored **2 or higher** requires **AIDEM Full**.
- Any factor scored **3** forces minimum **High** risk.
- If all factors are 0–1, AIDEM Lite may be used if the work is familiar and reversible.

---

## Confidence and range width

AIDEM tracks both calibration and sharpness.

```text
Range Width % = (High Estimate - Low Estimate) / Midpoint Estimate
```

| Confidence tier | Target max range width |
|---|---:|
| High | ≤ 25% |
| Medium | ≤ 40% |
| Low | ≤ 60% |

Every dashboard metric should also show sample size `n`.

Rule:

> Do not treat a tier-level calibration result as stable until it has at least 10 completed tickets.

---

## Repository structure

```text
/docs
  aidem-framework.md
  pilot-addendum.md
  dashboard-patch.md
/templates
  jira-template.md
  lite-template.md
  full-template.md
/examples
  example-library.md
/governance
  risk-scorecard.md
  remediation-playbooks.md
```

---

## Recommended pilot

Run AIDEM for one quarter before making major framework changes.

Track:

- estimate range vs actual
- confidence calibration by tier
- median range width by tier
- sample size `n`
- grooming time per ticket
- AIDEM-H share of tickets
- Lite vs Full usage
- review/rework effort
- defects and escaped defects
- AI tooling incidents

---

## What AIDEM does not do

AIDEM is downstream of portfolio selection.

It helps estimate, groom, govern, and calibrate work that has already entered the delivery pipeline. It does not decide whether AI has changed what work is worth doing. Portfolio selection, opportunity discovery, and product strategy require separate decision frameworks.

---

## License

This project is shared under the **Creative Commons Attribution 4.0 International License** for documentation and framework content.

Templates may be adapted freely with attribution.

---

## Contributing

Feedback is welcome, especially from engineering leaders, tech leads, product leaders, and engineers using AI-assisted delivery in real teams.

Useful contributions include:

- pilot results
- alternative risk scoring methods
- examples from real engineering workflows
- improvements to Lite vs Full usage
- confidence calibration lessons
- critiques of where the framework becomes too heavy

See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidance.
