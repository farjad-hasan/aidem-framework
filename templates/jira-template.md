# AIDEM Jira Template

Use this template during backlog refinement or sprint planning.

---

## 1. Mode selection

AIDEM mode:

- [ ] AIDEM-T — Transition Mode
- [ ] AIDEM-N — Native Mode
- [ ] AIDEM-H — Hybrid Mode

Template level:

- [ ] Lite
- [ ] Full

---

## 2. 30-second Lite/Full risk pre-check

Score the four 2x risk factors before choosing Lite.

| Factor | Score 0–3 |
|---|---:|
| Production data impact |  |
| Customer-facing impact |  |
| Reversibility concern |  |
| Security/privacy concern |  |

Rules:

- Any score 2 or higher requires AIDEM Full.
- Any score of 3 forces minimum High risk.

---

## 3. Estimate range and confidence

Estimate low:

Estimate high:

Midpoint:

Range width %:

```text
(High - Low) / Midpoint
```

Confidence:

- [ ] High
- [ ] Medium
- [ ] Low

Target max range width:

| Confidence | Max range width |
|---|---:|
| High | 25% |
| Medium | 40% |
| Low | 60% |

---

## 4. AIDEM-T details, if applicable

Base estimate without AI:

AI-eligible work:

AI leverage assumption:

Non-AI work:

Context setup:

Review:

Testing:

Rework:

Flow overhead:

Risk multiplier:

Final estimate range:

---

## 5. AIDEM-N details, if applicable

Reference class used:

Similar completed tickets/examples:

Reference estimate range:

Validation effort:

Flow overhead:

Risk buffer:

Final estimate range:

---

## 6. Hybrid mode guardrail, if applicable

Named transition-mode sub-tasks:

- 

Named native-mode sub-tasks:

- 

No duplicate overhead confirmation:

- [ ] Validation, flow, and risk are counted once at the whole-ticket level unless a sub-task has a distinct release path.

---

## 7. Skill-development mode

Choose one:

- [ ] AI-assisted delivery — AI may be used throughout with normal review expectations.
- [ ] Human-first learning task — engineer attempts first solution manually, then uses AI for review/comparison/refinement.
- [ ] Pair with AI review — AI is used as reviewer/explainer; implementation decisions remain with the engineer.
- [ ] Senior-guided implementation — senior reviewer guides before heavy reliance on AI output.

---

## 8. Completion review

Actual effort:

Actual landed inside range?

- [ ] Yes
- [ ] No

Range width acceptable for confidence tier?

- [ ] Yes
- [ ] No

Grooming time spent:

Defects/rework notes:

Remediation triggered?

- [ ] Yes
- [ ] No

Notes:
