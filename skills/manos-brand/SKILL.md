---
name: manos-brand
description: Manos brand identity and voice system. Apply this skill to ALL content created for Manos — written content, documents, presentations, design assets, web pages, UI components, social graphics, and any other output that represents the Manos brand. This skill should trigger whenever someone is creating, editing, or reviewing anything for Manos, including blog posts, LinkedIn posts, Substack essays, website copy, pitch decks, reports, PDFs, landing pages, dashboards, email templates, social media graphics, banners, or any branded deliverable. If the work is for Manos, this skill applies. No exceptions.
metadata:
  version: 1.0.0
---

# Manos Brand System

This skill defines how Manos looks, sounds, and feels across every output. Read the relevant reference files before creating any Manos content.

## Quick Reference

### Logo

The Manos logo is a custom lowercase serif wordmark. SVG source:

```
https://raw.githubusercontent.com/Manos-Agents/HQ-marketing-skills/main/assets/manos-black-V2.svg
```

Two official pairings only — never use the logo outside these combinations:

- **Official:** Dark Pine (#1F271B) wordmark on Linen Grey (#ECEDEA) background
- **Secondary:** Charcoal Smoke (#191A1E) wordmark on Soft Stone (#F8F6F2) background

Minimum clear space: cap-height of the "m" on all sides. Minimum size: 80px wide (digital), 25mm wide (print). Submark variations are TBD — always use the full wordmark.

### Colors

| Name | Hex | RGB | Role |
|------|-----|-----|------|
| Dark Pine | #1F271B | rgb(31, 39, 27) | Primary brand color. Headers, primary text, hero backgrounds. |
| Charcoal Smoke | #191A1E | rgb(25, 26, 30) | Deep neutral. Footers, secondary dark surfaces. |
| Sage Stone | #D8DDD4 | rgb(216, 221, 212) | Soft accent. Section backgrounds, card fills, dividers. |
| Slate | #3E4A4F | rgb(62, 74, 79) | Structural accent. Secondary headings, captions, UI elements. |
| Linen Grey | #ECEDEA | rgb(236, 237, 234) | Light background. Content areas, cards. |
| Soft Stone | #F8F6F2 | rgb(248, 246, 242) | Warmest neutral. Primary page background, hero sections. |

**Usage rules:**
- Dark Pine dominates — it carries the most visual weight in any composition.
- Do not use Dark Pine and Charcoal Smoke at equal weight in the same layout.
- Do not use Sage Stone for text — insufficient contrast on light backgrounds.
- Slate works for secondary body text on light backgrounds when Dark Pine feels too heavy.

### Typography

- **IBM Plex Sans** — headlines, titles, navigation, UI, labels. The structural typeface.
- **Geist** — body copy, long-form content, captions, descriptions. The narrative typeface.

No third typeface in any layout. All-caps reserved for short labels only. Minimum body text: 16px digital, 10pt print.

### Voice (Summary)

Structural. Measured. Grounded. Disciplined. For full voice rules including altitude modes, fetch the voice system from GitHub (see Reference Files below).

**Core constraints:** Declarative sentences. No buzzwords. No hype. No em dashes. AI is embedded infrastructure, never magic. Every claim must be measurable or structurally explainable. Clarity over cleverness. Specificity over abstraction.

## How to Apply This Skill

### Written Content (blog posts, LinkedIn, Substack, website copy)

1. Fetch and read the voice system before writing:
   ```bash
   curl -o manos-voice.md "https://raw.githubusercontent.com/Manos-Agents/HQ-marketing-skills/main/references/manos-voice.md"
   ```
2. Identify which voice altitude applies (Institutional, Operator Group, or Operator Builder).
3. Follow the sentence style, emphasis, and avoidance rules.
4. Every piece must reinforce the Core Thesis and align to one Primary Pillar.
5. No filler. Every sentence advances the argument.

### Documents (decks, PDFs, reports)

1. Use the color palette above for all backgrounds, text, and accents.
2. Set headings in IBM Plex Sans, body text in Geist.
3. Apply the logo in one of the two official pairings on title slides or cover pages. Fetch the SVG from GitHub (see Reference Files below).
5. Write all copy in Manos voice — fetch and read the voice system from GitHub (see Reference Files below).

### Design Assets (social graphics, banners, templates)

1. Only use colors from the palette above. No off-brand colors.
2. Logo must appear in one of the two official pairings.
3. Typography: IBM Plex Sans for headlines, Geist for supporting text.
4. Maintain generous whitespace. The brand aesthetic is restrained, not dense.
5. No effects on the logo — no shadows, outlines, glows, rotations.

### Code / UI (web pages, components, dashboards)

1. Use CSS variables mapped to the palette:
   ```css
   :root {
     --manos-dark-pine: #1F271B;
     --manos-charcoal-smoke: #191A1E;
     --manos-sage-stone: #D8DDD4;
     --manos-slate: #3E4A4F;
     --manos-linen-grey: #ECEDEA;
     --manos-soft-stone: #F8F6F2;
   }
   ```
2. Import fonts:
   ```css
   @import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Sans:wght@400;500;600;700&display=swap');
   ```
   For Geist, load from the Vercel CDN or bundle locally.
3. Default page background: Soft Stone. Secondary sections: Linen Grey.
4. Primary text: Dark Pine on light backgrounds, white on Dark Pine/Charcoal Smoke.
5. All UI copy follows Manos voice constraints.

## Reference Files (GitHub)

All brand references are maintained in the Manos HQ repo. Fetch the ones you need before starting work.

### Voice System
Full voice rules with altitude modes, narrative patterns, conversion guardrails, and writing rules. Fetch before writing any Manos content.
```bash
curl -o manos-voice.md "https://raw.githubusercontent.com/Manos-Agents/HQ-marketing-skills/main/references/manos-voice.md"
```

### Brand Guidelines
Complete brand guidelines with detailed logo rules, color accessibility pairings, type scale, and misuse examples. Fetch when you need precise visual specifications.
```bash
curl -o manos-brand-guidelines.md "https://raw.githubusercontent.com/Manos-Agents/HQ-marketing-skills/main/references/manos-brand-guidelines.md"
```

### Logo SVG
```bash
curl -o manos-logo.svg "https://raw.githubusercontent.com/Manos-Agents/HQ-marketing-skills/main/assets/manos-black-V2.svg"
```
