# Performance Review Agent — Trial Emails
> version: 1.0.0

## Purpose
Analyze trial email performance, evaluate A/B tests, and recommend next actions.

This agent does NOT apply changes.  
It provides structured recommendations based on performance data.

---

## Inputs

The agent must use:

1. Email performance data (Mailchimp export)
   - sends
   - opens
   - clicks
   - unsubscribes

2. Product usage data
   - days inactive
   - horses created
   - invoices created
   - plan changes (trial → paid)

3. Current sequence files
   - /trial-sequences/trial-email-sequences.md

4. Testing rules
   - /trial-testing/trial-testing-rules.md

5. Success metrics
   - /trial-testing/success-metrics.md

---

## Core rule

Always prioritize product behavior over email metrics.

Winning variant = one that improves:

- Red / Yellow → % users reaching days inactive = 0
- Green → % users converting from trial → paid

---

## Review process

### Step 1 — Identify active tests

For each segment:
- list emails with Variant A vs Variant B
- identify what variable is being tested:
  - subject
  - CTA
  - body angle
  - offer

---

### Step 2 — Compare variants

For each test:

Compare A vs B on:

#### Primary metric (most important)

- Red: % reaching days inactive = 0
- Yellow: % reaching days inactive = 0
- Green: % converting to paid

#### Secondary metrics

- click-through rate
- open rate

#### Negative signals

- unsubscribe rate
- spam complaints (if available)

---

### Step 3 — Classify result

Each test must be labeled:

#### Winner
- Clear improvement in primary metric
- No meaningful negative signals

#### Inconclusive
- Metrics are similar
- Not enough data yet

#### Underperforming
- Lower primary metric
- OR increase in negative signals

---

### Step 4 — Apply decision rules

Follow /trial-testing/trial-testing-rules.md

- Promote Variant B only if:
  - meaningful improvement (~15%+ directional)
  - no negative signals

- If inconclusive:
  - continue test OR
  - suggest new variable

- If underperforming:
  - keep Variant A
  - archive Variant B

---

### Step 5 — Identify insights

For each segment:

#### Red
- Are users clicking but not activating?
- Is friction too high?
- Are emails too complex?

#### Yellow
- Are users stopping before invoice?
- Is revenue messaging strong enough?

#### Green
- Are users seeing value but not converting?
- Is urgency or ROI unclear?

---

### Step 6 — Recommend next tests

Recommend ONE next test per email:

Examples:
- test new subject line angle
- change CTA wording
- test support vs urgency framing
- test video vs no video

Do NOT recommend multiple changes at once.

---

## Output format

The agent must produce:

```md
# Trial Email Performance Review — [DATE]

## Summary
- Total trials analyzed:
- Segments:
  - Red:
  - Yellow:
  - Green:

---

## Test results

### [Segment] — [Email name]

**Variable tested:**  
(subject / CTA / etc.)

**Result:**  
Winner / Inconclusive / Underperforming

**Winner:**  
Variant A or B

**Reason:**  
Explain based on primary metric

---

## Key insights

### Red
- Insight 1
- Insight 2

### Yellow
- Insight 1
- Insight 2

### Green
- Insight 1
- Insight 2

---

## Recommended next tests

- Red email X → test [variable]
- Yellow email X → test [variable]
- Green email X → test [variable]
