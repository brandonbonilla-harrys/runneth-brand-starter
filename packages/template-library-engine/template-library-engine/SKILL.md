---
name: template-library-engine
description: |
  Build and grow the brand's static-ad template library: harvest competitor and inspiration
  statics, vision-classify them, dedupe against what's already in the pool, and mint genuinely
  net-new reference-only layout-IP templates the static-ad flow can reuse. Use when someone says
  "mint a template", "new template", "harvest inspo formats", "add a template to the library",
  "find new static formats", "discover competitor formats", or "refresh the template library".
  Reads the brand-product profile. Requires brand-product-foundation.
---

# template-library-engine

The operating procedure lives in the brain docs this package installs:

1. Read `/agent/brain/template-library-engine/sop.md` for the harvest, classify, dedupe, and mint
   steps.
2. Read the brand-product profile for products and brand context. If missing, route to
   `brand-product-foundation`.

## Key rules

- Templates are layout IP, reference-only: they capture structure/composition, never a specific
  product render. The static-ad flow supplies product fidelity from reference images at generation
  time.
- Dedupe every candidate against the existing pool before minting; only genuinely net-new layouts
  get added.
- Keep competitor source attribution on harvested examples.
