# Trial Success Metrics — StableTrack
> version: 1.0.0

## Purpose
Define the primary success condition for each engagement segment.

All testing, reporting, and iteration decisions must prioritize product behavior over email metrics.

---

## Red (low engagement)

### Goal
Move user from inactive → active

### Success definition
Days inactive = 0

### Interpretation
User has taken a meaningful action in the product:
- created first horse
- logged activity
- started using the system

### Primary metric
% of users reaching 0 days inactive

---

## Yellow (medium engagement)

### Goal
Drive activity and complete workflow

### Success definition
Days inactive = 0

### Interpretation
User has resumed activity and progressed in the workflow:
- logged treatment
- generated invoice (preferred)

### Primary metric
% of users reaching 0 days inactive

### Secondary signal
- invoice creation rate

---

## Green (high engagement)

### Goal
Convert trial → paid

### Success definition
Plan changes from trial → basic

### Interpretation
User has:
- experienced value
- committed to using the product

### Primary metric
% of users converting to paid

---

## Metric hierarchy

### Red
1. Days inactive = 0
2. Click-through rate
3. Open rate

### Yellow
1. Days inactive = 0
2. Invoice creation (secondary)
3. Click-through rate
4. Open rate

### Green
1. Trial → paid conversion
2. Click-to-paid rate
3. Click-through rate
4. Open rate

---

## Evaluation rules

- Winning variant = one that improves primary metric
- Do not prioritize open rate over product behavior
- Click-through rate is only meaningful if it leads to product usage

---

## Low-volume testing rules

- First full review after 50 total trial users
- Allow full 14-day trial window before evaluating
- Use directional signals:
  - Promising
  - Flat
  - Concerning

- Do not over-rotate variants early

---

## Notes

- Email performance is a proxy, not the goal
- Success is defined by behavior change in the product
- All lifecycle messaging must align with real product usage
