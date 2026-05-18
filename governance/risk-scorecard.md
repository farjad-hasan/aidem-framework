# AIDEM Risk Scorecard

Use this scorecard for AIDEM Full tickets.

---

## Weighted risk factors

| Risk factor | Score 0–3 | Weight |
|---|---:|---:|
| Production data impact | 0–3 | 2x |
| Customer-facing impact | 0–3 | 2x |
| Reversibility concern | 0–3 | 2x |
| Security/privacy concern | 0–3 | 2x |
| Number of integrated systems | 0–3 | 1x |
| Test coverage availability | 0–3 | 1x |
| Stakeholder ambiguity | 0–3 | 1x |
| AI tooling dependency | 0–3 | 1x |

---

## Severity floor rule

If any 2x-weighted factor scores 3, the ticket has a minimum risk level of High regardless of total score.

This applies to:

- production data impact
- customer-facing impact
- reversibility concern
- security/privacy concern

---

## Suggested score interpretation

| Score | Meaning |
|---:|---|
| 0 | No meaningful concern |
| 1 | Low concern; standard review is enough |
| 2 | Moderate concern; requires Full template and explicit validation |
| 3 | Severe concern; minimum High risk and governance gate required |

---

## Suggested risk bands

Use these bands as a starting point. Teams should calibrate them during pilot.

| Weighted score | Risk level |
|---:|---|
| 0–4 | Low |
| 5–9 | Medium |
| 10–15 | High |
| 16+ | Critical |

Severity floor overrides the weighted score.

---

## Governance gates for High/Critical work

High or Critical work should include:

- assigned reviewer
- test plan
- rollback plan
- monitoring/logging consideration
- deployment owner
- approval owner
- explicit failure modes where relevant
