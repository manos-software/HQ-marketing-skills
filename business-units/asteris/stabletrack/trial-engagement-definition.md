# Trial Engagement Definition — StableTrack
> version: 1.2.1

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
| yellow | Medium engagement | User started but incomplete | Drive activity and workflow completion |
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
→ Convert trial to paid plan

---

### Medium engagement (yellow)

Criteria:
- Created 1–4 horses
- Some activity
- No invoice generated

Interpretation:
- User is exploring
- Has not reached full value yet

Primary goal:
→ Drive activity and complete workflow

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

If using Slack:
- Download the latest report shared by the team
- Save as: engagement-report.csv

---

### Step 2 — Filter trial users

- Identify users currently in trial (14-day window)
- Remove:
  - expired trials
  - paying customers

Output:
→ trial-only dataset

---

### Step 3 — Map engagement to segments

For each user:

- green → High engagement
- yellow → Medium engagement
- red → Low engagement

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

### Step 5 — Sync to Mailchimp

Upload lists and apply tags:

- stabletrack_trial_green
- stabletrack_trial_yellow
- stabletrack_trial_red

Trigger corresponding automations.

---

## Instructions for agents

- Always check engagement segment first
- Never send generic sequences across segments
- Adapt messaging:
  - Red → simplify + guide + support
  - Yellow → drive activity + workflow completion
  - Green → reinforce value + convert

- If engagement data is missing:
  → default to LOW engagement
