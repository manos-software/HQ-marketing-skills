# StableTrack Intelligence — README

> Brand, product, and market intelligence for StableTrack skills and agents.
> All files are prefixed `stabletrack-` to support multi-product scaling.

---

## How this system works

**Hub and spoke.** One lean hub file carries the brand identity, voice, values, and visual specs that every skill needs. Five reference files carry deeper context that skills load selectively based on the task.

This keeps context usage low. The hub file is ~1,500 words. A skill writing a cold email loads the hub + ICP (~2,100 words total) instead of a 9,000-word monolith.

---

## Folder map

```
stabletrack-intelligence/
│
├── README.md                                         ← You are here
│
├── stabletrack-brand-intelligence.md                 ← HUB FILE (read always)
│   Identity, positioning, values, AI trust framework,
│   voice & tone, visual identity, narrative constraints.
│   Every skill reads this before generating output.
│
└── references/                                       ← SPOKE FILES (read selectively)
    │
    ├── stabletrack-market-context.md                 ← Industry data, workforce crisis,
    │                                                    revenue leakage research, JAVMA study
    │
    ├── stabletrack-competitive-landscape.md          ← Competitor profiles, positioning matrix,
    │                                                    competitive moat, vulnerability analysis
    │
    ├── stabletrack-icp.md                            ← Firmographics, demographics, pain points,
    │                                                    buying triggers, objection handling, segments
    │
    ├── stabletrack-product.md                        ← Modules, features, integrations, differentiators,
    │                                                    release notes, product maturity
    │
    └── stabletrack-gtm.md                            ← Outbound persona, campaign structure, lead sources,
                                                         TAM, sales cycle, content strategy, proof points,
                                                         strategic narrative
```

---

## Which files to load by task

| Task | Load |
|------|------|
| Any StableTrack content | `stabletrack-brand-intelligence.md` (always) |
| Cold email / outbound sequence | + `stabletrack-icp.md` + `stabletrack-gtm.md` |
| Blog post / content marketing | + `stabletrack-market-context.md` |
| Competitor comparison / battle card | + `stabletrack-competitive-landscape.md` |
| Product page / feature copy | + `stabletrack-product.md` |
| Pitch deck / investor content | + `stabletrack-market-context.md` + `stabletrack-product.md` |
| Ad copy / social media | + `stabletrack-icp.md` |
| Sales enablement / demo prep | + `stabletrack-competitive-landscape.md` + `stabletrack-product.md` |
| CRO / landing page optimization | + `stabletrack-icp.md` + `stabletrack-product.md` |
| Campaign strategy / planning | + `stabletrack-gtm.md` + `stabletrack-icp.md` |

---

## Rules

1. **Always read the hub file first.** No StableTrack output should be generated without loading `stabletrack-brand-intelligence.md`.
2. **Load reference files only when needed.** Don't load all five for a simple email. Match files to task.
3. **Never duplicate reference content into the hub file.** The hub stays lean. If you need market stats, load the market context file — don't copy the stats into the hub.
4. **Namespace all files.** Every file in this folder starts with `stabletrack-`. As other products/business units are added, they will follow the same pattern (e.g., `keystone-brand-intelligence.md`).
5. **Version the hub file.** The hub has a version number in its frontmatter. Update it when the brand, positioning, voice, or visual identity changes. Reference files can be updated independently.

---

## Maintenance

- **Hub file** — update when brand identity, values, voice, visual specs, or positioning changes. These change infrequently.
- **Reference files** — update when the underlying data changes (new competitors, new features, new market research, new campaign structure). These change more often.
- **Adding a new product** — create a new folder (e.g., `keystone-intelligence/`) with the same hub-and-spoke structure. Prefix all files with the product name.
