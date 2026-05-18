# AIDEM Framework

**AIDEM** stands for **AI-Assisted Delivery Estimation Model**.

It is a dual-mode grooming and calibration protocol for AI-assisted engineering delivery.

AIDEM helps teams estimate and discuss work by making these factors explicit:

- delivery mode
- AI assistance pattern
- validation burden
- flow overhead
- confidence
- range width
- risk
- calibration from actual outcomes

AIDEM should not be used as a precision formula. It is designed to improve the quality of estimation conversations and create better feedback loops from completed work.

---

## Core principle

AI does not make all software work uniformly faster.

It changes the shape of work:

- some tasks accelerate
- some tasks shift from writing to reviewing
- some tasks require more validation
- some work remains judgment-heavy
- some work becomes possible that was previously too expensive

AIDEM keeps those differences visible.

---

## AIDEM-T: Transition Mode

Use **AIDEM-T** when the team has credible experience estimating similar work before AI assistance.

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

### When to use AIDEM-T

Use it when:

- the team knows how similar work was estimated before AI
- the AI-assisted portion can be reasonably separated
- the ticket has a meaningful pre-AI historical baseline
- the team is still transitioning into AI-assisted workflows

### When not to use AIDEM-T

Avoid it when:

- the team is already AI-native
- the non-AI baseline is hypothetical
- AI is ambient throughout the work
- the AI-eligible split would be invented

---

## AIDEM-N: Native Mode

Use **AIDEM-N** when the team is AI-native or when AI is ambient throughout the delivery process.

Formula:

```text
T_planning = T_reference + T_validation + T_flow + T_risk
```

### When to use AIDEM-N

Use it when:

- similar AI-assisted work has already been completed
- the team has reference-class data
- AI is continuously in the workflow
- there is no credible non-AI baseline

### Reference class examples

A reference class should include similar completed work, such as:

- similar API endpoint changes
- similar UI component work
- similar integration tasks
- similar migration or data work
- similar discovery or architecture spikes

The estimate should come from actual completed AI-assisted work, not from a hypothetical non-AI baseline.

---

## AIDEM-H: Hybrid Mode

Use **AIDEM-H** only when one ticket contains both transition-style and native-style work.

Hybrid mode must include a named split.

```text
Transition-mode sub-tasks:
- Legacy API update
- Known integration pattern

Native-mode sub-tasks:
- AI-assisted reference-class UI changes
- AI-assisted test expansion from prior examples
```

### No duplicate overhead rule

Validation, flow, and risk should be counted once at the whole-ticket level unless a sub-task has a distinct release path.

### Hybrid overuse guardrail

If AIDEM-H exceeds 30–40% of tickets in a pilot, review whether:

- tickets are too large
- the team is avoiding clearer mode selection
- AIDEM-T/N criteria need better examples
- hybrid work is genuinely common in the current delivery stream

---

## Risk scoring

AIDEM uses a weighted risk scorecard. High-impact risk factors receive stronger weighting.

| Risk factor | Weight |
|---|---:|
| Production data impact | 2x |
| Customer-facing impact | 2x |
| Reversibility concern | 2x |
| Security/privacy concern | 2x |
| Number of integrated systems | 1x |
| Test coverage availability | 1x |
| Stakeholder ambiguity | 1x |
| AI tooling dependency | 1x |

### Severity floor rule

If any 2x-weighted factor scores 3, the ticket has a minimum risk level of **High**, regardless of total score.

This prevents severe production, customer, reversibility, or security risk from being hidden by a low total score.

---

## Confidence and range width

AIDEM estimates should be expressed as ranges.

```text
Range Width % = (High Estimate - Low Estimate) / Midpoint Estimate
```

| Confidence tier | Target max range width |
|---|---:|
| High | ≤ 25% |
| Medium | ≤ 40% |
| Low | ≤ 60% |

A team should track both:

- whether actuals land inside the estimate range
- whether the range is narrow enough to be useful

Every metric should include sample size `n`.

---

## Model and tool drift

AI tooling changes over time.

AIDEM estimates should record the model/tool version used during estimation and delivery when relevant.

Rebaseline when:

- a major model upgrade changes output behavior
- an AI coding tool changes workflow materially
- rate limits or pricing change significantly
- tooling availability becomes unreliable
- reference-class performance stops matching recent outcomes

---

## Skill-development modes

Skill development should be explicit, especially for junior or transitioning engineers.

| Mode | Operational definition |
|---|---|
| AI-assisted delivery | AI may be used throughout with normal review expectations. |
| Human-first learning task | Engineer attempts the first solution manually, then uses AI for review, comparison, or refinement. |
| Pair with AI review | AI is used as a reviewer/explainer; implementation decisions remain with the engineer. |
| Senior-guided implementation | A senior reviewer guides the approach before heavy reliance on AI output. |

---

## Boundary: downstream of portfolio selection

AIDEM starts after work has entered the delivery pipeline.

It does not decide whether AI has changed what work is worth doing. Portfolio selection, opportunity discovery, product strategy, and roadmap prioritization require separate decision frameworks.
