# Trial Email Testing Rules — StableTrack
> version: 1.0.0

## Purpose
Define how trial email sequences are tested, evaluated, and improved over time.

This file applies to all stages:
- early (low volume)
- scaling (higher volume)

---

## Core principles

- Optimize for product behavior, not email metrics
- Test one variable at a time
- Always maintain a control version
- Learn directionally before optimizing statistically
- Do not over-rotate early

---

## Testing structure

For each email:

- Variant A = control
- Variant B = challenger

Traffic split:
- 50 / 50

---

## Variables to test (priority order)

### 1. Subject line
Primary driver of open rate

### 2. CTA wording
Primary driver of action

### 3. Opening hook
First 1–2 lines of email

### 4. Body angle
- revenue leakage
- ease/simplicity
- time-saving
- support/help

### 5. Offer (if applicable)
- trial extension
- onboarding call
- tutorial content

---

## Testing constraints

- Only test ONE major variable per experiment
- Do NOT change subject + body + CTA at the same time
- Do NOT remove the control version
- Do NOT rewrite entire sequence in one iteration

---

## Success metrics (by segment)

### Red (low engagement)
Primary:
- % users reaching days inactive = 0

Secondary:
- click-through rate
- open rate

---

### Yellow (medium engagement)
Primary:
- % users reaching days inactive = 0

Secondary:
- invoice creation rate
- click-through rate
- open rate

---

### Green (high engagement)
Primary:
- % users converting from trial → paid

Secondary:
- click-to-paid rate
- click-through rate
- open rate

---

## Evaluation framework

Classify results as:

### Promising
- Improvement in primary metric
- No increase in negative signals

### Flat
- No meaningful difference between variants

### Concerning
- Drop in primary metric
- Increase in negative signals

---

## Negative signals

Monitor:
- unsubscribe rate
- spam complaints
- bounce rate

If these increase significantly:
→ pause or revert variant

---

## Phase 1 — Low volume testing

Applies when:
- total trials < 50

### Rules

- First meaningful review after:
  - 50 total trial users
  - AND full 14-day trial window

- Use directional judgment:
  - Promising
  - Flat
  - Concerning

- Do NOT declare winners too early

- Prioritize learning over optimization

---

## Phase 2 — Scaling testing (future)

Applies when:
- consistent volume > 50 trials per cycle

### Rules

- Require minimum sample per variant (e.g. 100+)
- Promote winners based on consistent performance
- Introduce more granular testing:
  - send time
  - personalization
  - sequencing logic

---

## Decision rules

Promote Variant B only if:

- Primary metric improves meaningfully (~15%+ directional improvement)
- No major negative signals
- Enough data to trust the trend

If inconclusive:
- continue test OR
- test a different variable

If underperforming:
- keep Variant A
- archive Variant B

---

## Iteration cadence

### Weekly
- Review performance
- Identify trends
- Document insights
- Do not rush decisions

### Biweekly (or after threshold)
- Promote winners
- Launch next test

---

## Agent responsibilities

Agents must:

- Read current variants and test plan
- Evaluate performance using primary metrics
- Recommend ONE action per test:
  - promote
  - continue
  - revert
  - test new variable

Agents must NOT:

- Modify multiple variables at once
- Change positioning or ICP
- Remove control variants
- Apply changes without approval

---

## Versioning

Each sequence file must include:

- version
- date
- test variable

Example:

version: 1.0.0
change: subject line test  
date: 2026-03-21

---

## Notes

- Email performance is a proxy, not the goal
- Product usage defines success
- Consistency in testing > speed of iteration
