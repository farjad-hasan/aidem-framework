# AIDEM Remediation Playbooks

Use these playbooks when dashboard guardrails flag recurring problems.

---

## Hybrid overuse

**Trigger:** AIDEM-H is more than 40% of tickets.

**Likely causes:**

- tickets are too large
- mode criteria are unclear
- the team is defaulting to Hybrid when rushed
- genuinely mixed work is common in the current stream

**Remediation:**

1. Review five recent Hybrid tickets.
2. Reclassify into AIDEM-T or AIDEM-N where possible.
3. Split tickets that contain unrelated transition/native work.
4. Add examples to clarify mode selection.

---

## Confidence miss

**Trigger:** A confidence tier lands below target after at least 10 completed tickets.

**Remediation:**

1. Review tickets outside the range.
2. Identify whether misses came from requirements, technical uncertainty, flow delay, or rework.
3. Tighten confidence criteria.
4. Add discovery before commitment when needed.
5. Adjust range width only when uncertainty is real and explicit.

---

## Range too wide

**Trigger:** Median range width exceeds the target for that confidence tier.

**Remediation:**

1. Split the ticket.
2. Add a discovery spike.
3. Lower confidence if uncertainty is real.
4. Avoid using wide ranges only to improve in-range rate.

---

## Grooming overhead high

**Trigger:** Average grooming time exceeds the team’s agreed limit.

**Remediation:**

1. Use AIDEM Lite for low-risk, familiar, reversible work.
2. Reserve Full for consequential work.
3. Time-box mode selection.
4. Move deeper analysis into a spike if needed.

---

## High/Critical defect escape

**Trigger:** Any escaped defect on High or Critical work.

**Remediation:**

1. Review the risk scorecard.
2. Check whether the severity floor should have applied.
3. Review assigned reviewer and test evidence.
4. Update the release checklist.
5. Add missing failure modes to future tickets.

---

## AI tooling incidents

**Trigger:** Repeated outage, rate-limit, context, model, or tool failures.

**Remediation:**

1. Add fallback path.
2. Reduce AI dependency on critical path work.
3. Include dependency buffer when appropriate.
4. Track tool/model version and incident type.
5. Rebaseline reference classes after major model/tool changes.
