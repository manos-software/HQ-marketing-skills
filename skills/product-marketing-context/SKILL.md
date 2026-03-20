---
name: product-marketing-context
description: "When the user wants to create or update their product marketing context document. Also use when the user mentions 'product context,' 'marketing context,' 'set up context,' 'positioning,' 'who is my target audience,' 'describe my product,' 'ICP,' 'ideal customer profile,' or wants to avoid repeating foundational information across marketing tasks. Use this at the start of any new project before using other marketing skills — it creates `.agents/product-marketing-context.md` that all other skills reference for product, audience, positioning, and go-to-market context."
metadata:
  version: 1.0.0
---

# Product Marketing Context

You help users create and maintain a product marketing context document. This captures foundational positioning, messaging, and GTM information that other marketing skills reference, so users do not have to repeat themselves.

The document is stored at `.agents/product-marketing-context.md`.

## Workflow

### Step 1: Check for existing context

First, check if `.agents/product-marketing-context.md` already exists. Also check `.claude/product-marketing-context.md` for older setups. If found there but not in `.agents/`, offer to move it.

**If it exists:**
- Read it and summarize what is already captured
- Ask which sections they want to update
- Only gather information for those sections

**If it does not exist, offer two options:**

1. **Auto-draft from available materials** (recommended): Study the repo, README, landing pages, marketing copy, docs, pricing pages, package files, and other available materials, then draft a V1 of the context document. The user can then review, correct, and fill in gaps. This is faster than starting from scratch.

2. **Start from scratch**: Walk through each section conversationally, gathering information one section at a time.

Most users prefer option 1. After presenting the draft, ask: "What needs correcting? What is missing?"

### Step 2: Gather information

**If auto-drafting:**
1. Read available materials: README, landing pages, marketing copy, about pages, meta descriptions, pricing pages, docs, package files, and any existing notes
2. Draft all relevant sections based on what you find
3. Present the draft and ask what needs correcting or is missing
4. Iterate until the user is satisfied

**If starting from scratch:**
Walk through each section below conversationally, one at a time. Do not dump all questions at once.

For each section:
1. Briefly explain what you are capturing
2. Ask relevant questions
3. Confirm accuracy
4. Move to the next section

Push for verbatim customer language. Exact phrases are usually more valuable than polished descriptions because they reflect how buyers and users actually think and speak, which makes messaging more resonant.

---

## Sections to capture

### 1. Product overview
- One-line description
- What it does (2-3 sentences)
- Product category (what "shelf" it sits on and how buyers search for it)
- Product type (SaaS, AI add-on, marketplace, service, platform, etc.)
- Business model and pricing

### 2. Target audience
- Target company type (industry, size, stage, operating model)
- Target decision-makers (roles, departments)
- Primary use case (the main problem solved)
- Jobs to be done (2-3 things customers "hire" it for)
- Specific use cases or scenarios

### 3. Personas
If multiple stakeholders are involved in buying or using the product, capture for each:
- User
- Champion
- Decision-maker
- Financial buyer
- Technical influencer
- Executive stakeholder

For each, capture:
- What they care about
- Their challenge
- The value promised to them

### 4. Problems and pain points
- Core challenge buyers face before finding the product
- Why current solutions fall short
- What it costs them (time, money, risk, missed revenue, inefficiency)
- Emotional tension (stress, uncertainty, frustration, internal pressure)

### 5. Competitive landscape
- **Direct competitors**: Same solution, same problem
- **Secondary competitors**: Different solution, same problem
- **Indirect competitors**: Status quo, internal workflows, agencies, spreadsheets, manual work, no decision
- How each falls short for this customer

### 6. Differentiation
- Key differentiators (capabilities or strengths alternatives lack)
- How the product solves the problem differently
- Why that is better
- Why customers choose it over alternatives

### 7. Objections and anti-personas
- Top 3 objections heard in sales, onboarding, or evaluation and how to address them
- Who is not a good fit (anti-persona)

### 8. Buying and switching dynamics
Capture the forces shaping change:

- **Push**: What frustrations drive them away from the current solution
- **Pull**: What attracts them to this product
- **Habit**: What keeps them stuck with the current approach
- **Anxiety**: What worries them about switching, adopting, or buying

### 9. Customer language
- How buyers or users describe the problem, ideally verbatim
- How they describe the product or desired outcome, ideally verbatim
- Words and phrases to use
- Words and phrases to avoid
- Glossary of product-specific or industry-specific terms

### 10. Brand voice
- Tone (professional, direct, technical, conversational, etc.)
- Communication style (clear, confident, practical, strategic, plainspoken)
- Brand personality (3-5 adjectives)

### 11. Proof points
- Key metrics or results to cite
- Notable customers, segments, or logos
- Testimonial snippets
- Main value themes and supporting evidence

### 12. Goals
- Primary business goal
- Key conversion action
- Current metrics, if known
- Relevant GTM priority, if known (pipeline, activation, retention, expansion, awareness)

---

## Step 3: Create the document

After gathering information, create `.agents/product-marketing-context.md` with this structure:

```markdown
# Product Marketing Context

*Last updated: [date]*

## Product Overview
**One-liner:**
**What it does:**
**Product category:**
**Product type:**
**Business model:**

## Target Audience
**Target companies:**
**Decision-makers:**
**Primary use case:**
**Jobs to be done:**
-
**Use cases:**
-

## Personas
| Persona | Cares about | Challenge | Value we promise |
|---------|-------------|-----------|------------------|
| | | | |

## Problems and Pain Points
**Core problem:**
**Why alternatives fall short:**
-
**What it costs them:**
**Emotional tension:**

## Competitive Landscape
**Direct:** [Competitor] — falls short because...
**Secondary:** [Approach] — falls short because...
**Indirect:** [Alternative] — falls short because...

## Differentiation
**Key differentiators:**
-
**How we do it differently:**
**Why that is better:**
**Why customers choose us:**

## Objections
| Objection | Response |
|-----------|----------|
| | |

**Anti-persona:**

## Buying and Switching Dynamics
**Push:**
**Pull:**
**Habit:**
**Anxiety:**

## Customer Language
**How they describe the problem:**
- "[verbatim]"
**How they describe us or the desired outcome:**
- "[verbatim]"
**Words to use:**
**Words to avoid:**
**Glossary:**
| Term | Meaning |
|------|---------|
| | |

## Brand Voice
**Tone:**
**Style:**
**Personality:**

## Proof Points
**Metrics:**
**Customers:**
**Testimonials:**
> "[quote]" — [who]
**Value themes:**
| Theme | Proof |
|-------|-------|
| | |

## Goals
**Business goal:**
**Conversion action:**
**Current metrics:**
**GTM priority:**
```

---

## Step 4: Confirm and save

- Show the completed document
- Ask if anything needs adjustment
- Save to `.agents/product-marketing-context.md`
- Tell them: "Other marketing skills will now use this context automatically. Run `/product-marketing-context` anytime to update it."

---

## Tips

- **Be specific**: Ask "What is the #1 frustration that brings them to you?" instead of "What problem do they solve?"
- **Capture exact words**: Customer language is usually more useful than polished descriptions
- **Ask for examples**: "Can you give me an example?" usually unlocks better answers
- **Validate as you go**: Summarize each section and confirm before moving on
- **Skip what does not apply**: Not every product needs every section
- **Adapt for B2B SaaS**: In portfolio environments, prioritize ICP clarity, value drivers, objections, use cases, and competitive alternatives
