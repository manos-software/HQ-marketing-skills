# HQ-1.0

Manos’s internal operating system for AI-assisted GTM, content, and operator execution.

---

## What this is

HQ-1.0 is a structured system of reusable skills, tools, and playbooks designed to support real execution inside vertical software businesses.

It is built for operators working across marketing, product, and revenue functions who want to use AI to accelerate output without losing context, quality, or control.

---

## Why this exists

AI makes it easier to generate output.

The value is not in prompts alone. It is in:
- understanding workflows  
- knowing what matters commercially  
- applying context from real systems and customers  

This system exists to bridge that gap.

---

## System map

Skills reference each other and build on shared context. The `product-marketing-context` skill is the foundation — every other skill checks it first to understand your product, audience, and positioning before doing anything.

```
                            ┌──────────────────────────────────────┐
                            │      product-marketing-context       │
                            │    (read by all other skills first)  │
                            └──────────────────┬───────────────────┘
                                               │
    ┌──────────────┬─────────────┬─────────────┼─────────────┬──────────────┬──────────────┐
    ▼              ▼             ▼             ▼             ▼              ▼              ▼
┌──────────┐ ┌──────────┐ ┌──────────┐ ┌────────────┐ ┌──────────┐ ┌─────────────┐ ┌───────────┐
│  SEO &   │ │   CRO    │ │Content & │ │  Paid &    │ │ Growth & │ │  Sales &    │ │ Strategy  │
│ Content  │ │          │ │   Copy   │ │Measurement │ │Retention │ │    GTM      │ │           │
├──────────┤ ├──────────┤ ├──────────┤ ├────────────┤ ├──────────┤ ├─────────────┤ ├───────────┤
│seo-audit │ │page-cro  │ │copywritng│ │paid-ads    │ │referral  │ │revops       │ │mktg-ideas │
│ai-seo    │ │signup-cro│ │copy-edit │ │ad-creative │ │free-tool │ │sales-enable │ │mktg-psych │
│site-arch │ │onboard   │ │cold-email│ │ab-test     │ │churn-    │ │launch       │ │           │
│programm  │ │form-cro  │ │email-seq │ │analytics   │ │ prevent  │ │pricing      │ │           │
│schema    │ │popup-cro │ │social    │ │            │ │          │ │competitor   │ │           │
│content   │ │paywall   │ │          │ │            │ │          │ │             │ │           │
└────┬─────┘ └────┬─────┘ └────┬─────┘ └─────┬──────┘ └────┬─────┘ └──────┬──────┘ └─────┬─────┘
     │            │            │              │             │              │              │
     └────────────┴─────┬──────┴──────────────┴─────────────┴──────────────┴──────────────┘
                        │
         Skills cross-reference each other:
           copywriting ↔ page-cro ↔ ab-test-setup
           revops ↔ sales-enablement ↔ cold-email
           seo-audit ↔ schema-markup ↔ ai-seo
```

See each skill's **Related Skills** section for the full dependency map.

---

## What are skills?

Skills are markdown files that give AI agents specialized knowledge and workflows for specific tasks.

When added to a project, they allow an agent to recognize the type of work being done and apply the right frameworks, structure, and best practices automatically.

---

## How skills work together

Skills are not used in isolation. They reference each other and build on shared context.

The `product-marketing-context` skill is the foundation. Every other skill checks it first to understand the product, audience, and positioning before generating output.

This ensures that all work stays consistent, relevant, and grounded in real business context.

---

## Available skills

| Skill | Category | Description |
|------|----------|------------|
| ab-test-setup | Paid & measurement | Plan, design, and implement A/B tests and experiments |
| ad-creative | Paid & measurement | Generate and iterate on ad creative across channels |
| ai-seo | SEO & content | Optimize content for AI search and LLM visibility |
| analytics-tracking | Paid & measurement | Set up and audit tracking, attribution, and measurement |
| churn-prevention | Growth & retention | Reduce churn through lifecycle and retention strategies |
| cold-email | Content & copy | Write B2B cold outreach and follow-up sequences |
| competitor-alternatives | Sales & GTM | Create comparison and alternative pages for SEO and sales |
| content-strategy | SEO & content | Plan content strategy and topic prioritization |
| copy-editing | Content & copy | Review and improve existing marketing copy |
| copywriting | Content & copy | Write and refine marketing copy across pages and assets |
| email-sequence | Content & copy | Build lifecycle, drip, and automated email flows |
| form-cro | CRO | Optimize lead capture and non-signup forms |
| free-tool-strategy | Growth & retention | Design free tools for acquisition and SEO |
| launch-strategy | Sales & GTM | Plan product and feature launches |
| lead-magnets | Growth & retention | Create assets for lead generation and capture |
| marketing-ideas | Strategy | Generate marketing strategies and campaign ideas |
| marketing-psychology | Strategy | Apply behavioral science to marketing decisions |
| onboarding-cro | CRO | Improve activation and onboarding flows |
| page-cro | CRO | Optimize conversion across marketing pages |
| paid-ads | Paid & measurement | Plan and execute paid acquisition campaigns |
| paywall-upgrade-cro | CRO | Optimize upgrade flows and monetization points |
| popup-cro | CRO | Design and improve popups and overlays |
| pricing-strategy | Sales & GTM | Define pricing, packaging, and monetization |
| product-marketing-context | Strategy | Define core product, audience, and positioning context |
| programmatic-seo | SEO & content | Build scalable SEO page systems |
| referral-program | Growth & retention | Design referral and word-of-mouth systems |
| revops | Sales & GTM | Manage lead lifecycle and revenue operations |
| sales-enablement | Sales & GTM | Create materials and systems for sales teams |
| schema-markup | SEO & content | Implement structured data for SEO |
| seo-audit | SEO & content | Audit and diagnose SEO performance |
| signup-flow-cro | CRO | Optimize registration and trial flows |
| site-architecture | SEO & content | Plan site structure and navigation |
| social-content | Content & copy | Create and optimize social media content |

---

## Usage

Once installed, ask your agent to help with specific marketing tasks:

"Help me optimize this landing page for conversions"  
→ uses `page-cro`

"Write homepage copy for my SaaS"  
→ uses `copywriting`

"Set up GA4 tracking for signups"  
→ uses `analytics-tracking`

"Create a 5-email welcome sequence"  
→ uses `email-sequence`

You can also invoke skills directly:

/page-cro  
/email-sequence  
/seo-audit  

---

## Skill categories

### Conversion optimization
- page-cro — marketing pages  
- signup-flow-cro — registration and trial flows  
- onboarding-cro — post-signup activation  
- form-cro — lead capture forms  
- popup-cro — modals and overlays  
- paywall-upgrade-cro — upgrade moments  

### Content & copy
- copywriting — marketing pages and assets  
- copy-editing — refine existing copy  
- cold-email — B2B outreach  
- email-sequence — lifecycle emails  
- social-content — social media  

### SEO & discovery
- seo-audit — technical and on-page SEO  
- ai-seo — AI search optimization  
- programmatic-seo — scalable SEO  
- site-architecture — navigation and structure  
- competitor-alternatives — comparison pages  
- schema-markup — structured data  

### Paid & distribution
- paid-ads — ad campaigns  
- ad-creative — creative iteration  
- social-content — distribution  

### Measurement & testing
- analytics-tracking — tracking and attribution  
- ab-test-setup — experiments  

### Growth & retention
- churn-prevention — retention systems  
- free-tool-strategy — acquisition tools  
- referral-program — referral systems  

### Strategy & monetization
- marketing-ideas — campaign ideas  
- marketing-psychology — behavioral frameworks  
- launch-strategy — launches  
- pricing-strategy — monetization  

### Sales & revops
- revops — lifecycle and pipeline  
- sales-enablement — sales materials  

---

## What’s inside

- `skills/` — reusable workflows and prompts  
- `tools/` — supporting execution tools  
- `AGENTS.md` — how agents operate  
- `CLAUDE.md` — Claude-specific behavior  
- `VERSIONS.md` — system evolution  

---

## How it’s used

This repository supports:

- GTM execution across the Manos portfolio  
- AI-assisted workflows for strategy and execution  
- development of Manos-native skills  
- internal enablement and fellowship training  

The focus is always on real outputs:
- campaigns shipped  
- positioning clarified  
- funnels improved  
- revenue impact  

---

## Principles

- Operator-first  
- Context over generic output  
- Speed with control  
- Systems over one-off prompts  
- Built for real workflows  

---

## Versioning

This repo is actively evolving and was created by Karine LaRocque on March 19, 2026.

All updates are tracked in `VERSIONS.md`.

---

## Direction

HQ-1.0 is evolving into a unified system for:

- AI-native GTM execution  
- portfolio-level marketing infrastructure  
- vertical AI positioning  
- operator training  
