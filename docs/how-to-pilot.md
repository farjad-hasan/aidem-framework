# How to Pilot AIDEM

This guide describes a practical one-quarter pilot.

---

## Pilot duration

Run the pilot for one quarter before making major framework changes.

A shorter pilot can reveal usability issues, but it is usually not enough to calibrate confidence, reference classes, or throughput.

---

## Pilot scope

Start with one team or one delivery stream.

Good candidates:

- a team already using AI tools
- a team with active grooming discipline
- a team with a mix of UI, API, integration, and discovery work
- a team willing to track actuals honestly

---

## Sprint 1: Setup

Actions:

1. Introduce AIDEM modes: T, N, and H.
2. Use Lite for low-risk tickets.
3. Use Full for High/Critical or uncertain work.
4. Start capturing estimate ranges and confidence.
5. Track grooming time per ticket.

Do not change sprint capacity yet.

---

## Sprint 2: Instrumentation

Actions:

1. Track actuals against estimate ranges.
2. Capture range width.
3. Record sample size `n` for each metric.
4. Track AIDEM-H share of tickets.
5. Track review/rework and defects.

---

## Sprint 3: Calibration review

Actions:

1. Review confidence calibration by tier.
2. Review median range width by tier.
3. Review Hybrid overuse.
4. Review Lite vs Full usage.
5. Review grooming time.
6. Apply remediation playbooks where needed.

---

## Quarter-end review

At the end of the quarter, review:

- Did AIDEM improve grooming conversations?
- Did estimates become more honest?
- Did the team avoid blanket AI productivity assumptions?
- Did High/Critical work receive better governance?
- Did AIDEM add too much overhead?
- Did AIDEM-H become overused?
- Were confidence tiers calibrated?
- Were ranges sharp enough to plan against?

---

## Metrics to track

| Metric | Purpose |
|---|---|
| Estimate low/high | Range-based planning |
| Actual effort | Calibration |
| Confidence tier | Forecast reliability |
| Range width % | Estimate sharpness |
| Sample size n | Preventing overreaction to noise |
| AIDEM mode | Mode discipline |
| Lite vs Full | Grooming overhead management |
| Grooming time | Operability |
| Review/rework effort | AI validation burden |
| Defects | Quality signal |
| Escaped defects | Governance signal |
| AI tooling incidents | Dependency risk |

---

## Capacity discussion

Do not use AIDEM to immediately cut or increase capacity.

Use team-level data for capacity conversations:

- throughput
- cycle time
- escaped defects
- review/rework ratio
- work-in-progress
- AI tooling incidents
- quality trends

Capacity is a team-level question, not a per-ticket leverage calculation.
