# Trial Engagement Definition — StableTrack
>version: 1.2.0

## Purpose
Segment trial users based on real product usage to drive personalized email sequences.

This file also defines how to operationalize segmentation using the engagement report.

---

## Source of truth

Engagement status is derived from the internal usage report exported as a CSV file.

Each user is labeled:
- green
- yellow
- red

---

## Mapping to trial segments

| Status | Segment | Meaning | Goal |
|--------|--------|--------|------|
| green  | High engagement | User reached value | Convert to paid |
| yellow | Medium engagement | User started but incomplete | Push to invoice |
| red    | Low engagement | User inactive or blocked | Drive first action |

---

## Segment definitions

### High engagement (green)

Criteria (any):
- Generated at least 1 invoice
- Completed workflow (horse → treatment → invoice)
- Multiple active sessions

Interpretation:
- User understands product
- Has experienced value

Primary goal:
→ Convert to paid

---

### Medium engagement (yellow)

Criteria:
- Created 1–4 horses
- Some activity
- No invoice generated

Interpretation:
- User is exploring
- Has not reached value yet

Primary goal:
→ Push to first invoice

---

### Low engagement (red)

Criteria:
- 0 horses created
- OR only logged in once
- OR no meaningful actions completed

Interpretation:
- User is blocked, confused, or disengaged

Primary goal:
→ Drive first action (create horse)

---

## Operational workflow

### Step 1 — Pull latest CSV

- Export the latest engagement report (CSV format)
- Ensure it includes:
  - user identifier (email or ID)
  - engagement status (green / yellow / red)
  - usage data if available

- If using Slack:
  - Download the latest report shared by the team
  - Save as `engagement-report.csv`

---

### Step 2 — Filter trial users

- Identify users within active trial window (14 days)
- Remove:
  - expired trials
  - paying customers

Output:
→ trial-only dataset

---

### Step 3 — Map engagement to segments

For each user:

- If status = green → High engagement
- If status = yellow → Medium engagement
- If status = red → Low engagement

---

### Step 4 — Prepare for email workflows

Create segmented lists:

- list_high_engagement.csv
- list_medium_engagement.csv
- list_low_engagement.csv

Each should include:
- email
- name (if available)
- segment

---

### Step 5 — Sync to CRM / email tool

Upload lists into your email platform (e.g., HubSpot)

Assign:
- workflow: high engagement → conversion sequence
- workflow: medium engagement → activation sequence
- workflow: low engagement → recovery sequence

---

## Instructions for agents

When generating outputs:

1. Always check engagement segment first
2. Adapt messaging accordingly:
   - Low → simplify + guide + support
   - Medium → push to value (invoice)
   - High → reinforce ROI + convert

3. Never send generic sequences across segments

4. If engagement data is missing:
   → default to LOW engagement

---

## Notes

- This system runs on a rolling 14-day trial window
- Segmentation should be refreshed regularly (daily or biweekly)
- Accuracy of engagement data directly impacts conversion performance
