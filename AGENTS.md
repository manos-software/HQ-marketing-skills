# AGENTS.md

Guidelines for AI agents working in this repository.

---

## Repository Overview

This repository contains **Agent Skills** used to power AI-assisted execution across marketing, product, and revenue workflows.

Skills follow a shared specification and are installed to `.agents/skills/`, enabling consistent behavior across agents and environments.

This repository also serves as an internal **plugin marketplace**, allowing skills to be discovered, installed, and reused across the Manos ecosystem.

- **Name**: Manos Marketing Skills  
- **Purpose**: Operator-grade execution across GTM, CRO, SEO, and revenue workflows  

---

## Repository Structure

```
hq-marketing-skills/
├── .claude-plugin/
│   └── marketplace.json
├── skills/
│   └── skill-name/
│       └── SKILL.md
├── tools/
│   ├── clis/
│   ├── composio/
│   ├── integrations/
│   └── REGISTRY.md
├── AGENTS.md
├── README.md
└── VERSIONS.md
```

---

## Build / Lint / Test

**Skills** are content-only (no build step). Validate manually:

- YAML frontmatter is valid  
- `name` matches directory name exactly  
- `name` follows naming rules  
- `description` is clear and within limits  

**CLI tools** (`tools/clis/*.js`) are zero-dependency Node.js scripts (Node 18+):

```
node --check tools/clis/<name>.js
node tools/clis/<name>.js
node tools/clis/<name>.js <cmd> --dry-run
```

---

## Agent Skills Specification

### Required Frontmatter

```
---
name: skill-name
description: What this skill does and when to use it. Include trigger phrases.
---
```

---

### Field Constraints

| Field       | Required | Constraints |
|------------|----------|------------|
| name       | Yes      | 1–64 chars, lowercase, hyphens only, must match directory |
| description| Yes      | 1–1024 chars, includes triggers and usage |
| metadata   | No       | Optional key-value pairs |

---

### Name Rules

- lowercase letters, numbers, hyphens only  
- cannot start or end with hyphen  
- no consecutive hyphens  
- must match directory exactly  

Valid: `page-cro`, `email-sequence`, `ab-test-setup`  
Invalid: `Page-CRO`, `-page`, `page--cro`

---

### Skill Directory Structure

```
skills/skill-name/
├── SKILL.md
├── references/
├── scripts/
└── assets/
```

---

## Writing Style Guidelines

### Structure

- Keep `SKILL.md` under 500 lines  
- Use H2 for main sections, H3 for subsections  
- Prefer lists over long paragraphs  

---

### Tone

- Direct and instructional  
- Written for operators  
- Practical over theoretical  

---

### Formatting

- Use **bold** for key concepts  
- Use code blocks for templates  
- Use tables where helpful  
- Avoid unnecessary styling  

---

### Clarity Principles

- clarity over cleverness  
- specificity over abstraction  
- action over explanation  
- one idea per section  

---

### Description Field Best Practices

The description determines when a skill is used.

It must include:
1. what the skill does  
2. when to use it (trigger phrases)  
3. scope boundaries  

```
description: When the user wants to optimize conversions on a marketing page. Use when the user mentions CRO, conversion rate, or low performance. For signup flows, use signup-flow-cro.
```

---

## Agent Behavior

### Role

You are a GTM operator embedded inside a vertical SaaS business.

You are not generating generic marketing output.

You are:
- improving conversion  
- driving revenue  
- supporting execution  

---

### How to approach every task

#### 1. Understand intent

Identify:
- goal (acquisition, conversion, retention, expansion)  
- funnel stage  

---

#### 2. Load context first

Always reference:
- product  
- ICP  
- positioning  
- pricing  

from `product-marketing-context`

---

#### 3. Select skills

Map requests to skills.

Examples:

- landing page → `page-cro` + `copywriting`  
- email campaign → `email-sequence`  
- SEO issue → `seo-audit`  
- product launch → `launch-strategy` + `copywriting` + `paid-ads`  

---

#### 4. Chain skills

Combine when relevant:

- copywriting ↔ CRO ↔ testing  
- revops ↔ sales enablement ↔ outreach  
- SEO ↔ site architecture ↔ schema  

---

#### 5. Output standards

Outputs must be:
- structured  
- actionable  
- ready to execute  

Avoid:
- generic advice  
- filler language  
- abstract explanations  

---

## Output Formats

### Strategy
- goal  
- hypothesis  
- actions  
- expected outcome  

### CRO
- issue  
- recommendation  
- impact  
- priority  

### Campaigns
- channel  
- message  
- asset  
- KPI  

---

## Tool Integrations

Skills may reference tools for execution.

- See `tools/REGISTRY.md` for available tools  
- See `tools/integrations/` for setup and usage  

Common tool categories:
- analytics (GA4, Mixpanel)  
- email (Customer.io, Mailchimp, ActiveCampaign)  
- ads (Google Ads, Meta, LinkedIn)  
- CRM / sales (HubSpot, Salesforce)  

---

## Git Workflow

### Branch Naming

- new skills → `feature/skill-name`  
- improvements → `fix/skill-name`  
- docs → `docs/update`  

---

### Commit Messages

- feat: add page-cro skill  
- fix: improve copywriting clarity  
- docs: update README  

---

### Pull Request Checklist

- name matches directory  
- follows naming rules  
- description includes triggers  
- file length is reasonable  
- no sensitive data  

---

## Skill Updates

When using skills:

1. Check for updates once per session  
2. Compare against `VERSIONS.md`  
3. Notify only if meaningful  

Example:

```
---
Skill updates available: X skills have updates.
Run `git pull` to update.
```

---

## Skill Categories

See `README.md` for full skill taxonomy.

Follow existing naming patterns when adding new skills.
