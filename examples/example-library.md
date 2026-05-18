# AIDEM Example Library

These examples are intentionally generic. Replace them with your own team’s reference data during pilot.

---

## Example 1: Customer-facing workflow update

### Context

A team needs to update a customer-facing contract or account workflow with several business rules and validation steps.

### Recommended mode

**AIDEM-T** if the team has historical estimates for similar workflow changes.

**AIDEM-N** if the team already has completed AI-assisted reference work for similar workflow changes.

### Notes

AI may help with:

- API scaffolding
- validation drafts
- test case drafts
- documentation

Human review remains important for:

- business rules
- customer impact
- edge cases
- data integrity

Risk is likely Medium or High depending on production and customer impact.

---

## Example 2: UI component from existing design system

### Context

A team needs to implement a reusable UI component using an existing component library and design token system.

### Recommended mode

**AIDEM-N** if the team has similar completed AI-assisted component work.

### Notes

AI may help significantly with:

- component scaffolding
- style mapping
- test drafts
- accessibility reminders

Validation remains important for:

- visual QA
- responsive behavior
- design consistency
- accessibility review

Likely Lite if low-risk and reversible.

---

## Example 3: Backend API endpoint with known patterns

### Context

A team needs to add a new backend endpoint following existing service, DTO, validation, and error-handling patterns.

### Recommended mode

**AIDEM-T** if the team can identify AI-eligible implementation effort.

**AIDEM-N** if similar AI-assisted endpoint work exists.

### Notes

AI may help with:

- DTOs
- validation
- controller/service scaffolding
- test case drafts

Human review remains important for:

- authorization
- data semantics
- integration assumptions
- error handling

Risk depends on data impact and customer-facing behavior.

---

## Example 4: Architecture or discovery spike

### Context

A team needs to evaluate design options and make a technical decision.

### Recommended mode

Usually **AIDEM-N** using reference-class forecasting from prior discovery spikes.

### Notes

AI may help with:

- option generation
- pros/cons analysis
- documentation
- diagram drafts
- research synthesis

Human judgment remains central for:

- tradeoff decisions
- stakeholder alignment
- long-term maintainability
- business context

Avoid claiming large AI productivity gains. Use ranges and confidence.

---

## Example 5: Production data migration

### Context

A team needs to migrate, relink, archive, or transform production data.

### Recommended mode

Usually **AIDEM Full** regardless of T/N/H mode.

### Notes

AI may help with:

- script drafts
- test data generation
- rollback checklist drafts
- validation query drafts

Human control is required for:

- production safety
- reversibility
- auditability
- dry-run validation
- rollback readiness

If production data impact scores 3, minimum High risk applies.
