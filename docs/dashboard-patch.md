# AIDEM Dashboard Patch

This patch adds operational controls for pilot tracking.

It does not change the AIDEM core formulas or mode structure.

---

## Range width target bands

AIDEM tracks whether actual work lands inside the estimate range and whether the range is sharp enough to plan against.

```text
Range Width % = (High Estimate - Low Estimate) / Midpoint Estimate
```

| Confidence tier | Target maximum range width | Interpretation |
|---|---:|---|
| High | ≤ 25% | Narrow enough for near-term planning |
| Medium | ≤ 40% | Useful for sprint planning with normal uncertainty |
| Low | ≤ 60% | Acceptable only when uncertainty is explicit |

If a confidence tier is calibrated but has widening range width, estimates are becoming safer but less useful.

---

## Sample size `n` per metric

Every dashboard metric should show the sample size behind it.

| Metric | Required `n` |
|---|---|
| High confidence in-range rate | Number of High confidence tickets |
| Medium confidence in-range rate | Number of Medium confidence tickets |
| Low confidence in-range rate | Number of Low confidence tickets |
| Median range width by tier | Number of tickets in that tier |
| AIDEM-H share | Total ticket count |
| Lite vs Full usage | Total ticket count |

Rule:

> Do not treat any tier-level calibration result as stable until it has at least 10 completed tickets.

---

## Lite/Full 30-second risk pre-check

AIDEM Lite is allowed only after a quick pre-check of the four 2x risk factors.

| Pre-check factor | Score |
|---|---:|
| Production data impact | 0–3 |
| Customer-facing impact | 0–3 |
| Reversibility concern | 0–3 |
| Security/privacy concern | 0–3 |

Rules:

- If any factor scores 2 or higher, use AIDEM Full.
- If any factor scores 3, the ticket has a minimum risk level of High.
- If all factors score 0–1, AIDEM Lite may be used if the ticket is familiar and reversible.

---

## Remediation playbooks

| Flag | Trigger | Remediation |
|---|---|---|
| Hybrid overuse | AIDEM-H > 40% of tickets | Review five Hybrid tickets, reclassify into T/N where possible, and split oversized tickets. |
| Confidence miss | Tier in-range below target after n ≥ 10 | Review estimate rationale, adjust confidence criteria, and improve discovery before commitment. |
| Range too wide | Median width above tier target | Split the ticket, add discovery, or lower confidence. |
| Grooming overhead high | Average grooming time above agreed limit | Use Lite for low-risk tickets and reserve Full for consequential work. |
| High/Critical defect escape | Any escaped defect on High/Critical ticket | Review governance gate, reviewer assignment, test evidence, and release checklist. |
| AI tooling incidents | Repeated tool outage, rate-limit, or context failures | Add fallback path, reduce critical-path dependency, or include dependency buffer. |

---

## What stays unchanged

- AIDEM-T formula remains unchanged.
- AIDEM-N reference-class approach remains unchanged.
- AIDEM-H remains the hybrid mode.
- Risk scorecard structure remains, with the severity floor retained.
- This patch is operational instrumentation, not a new framework version.
