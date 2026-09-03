---
name: brand-kit
description: |
  Build a complete brand kit for the brand (identity, visual system from computed site styles,
  voice and messaging, application patterns, anti-patterns) dense enough that another agent can
  produce on-brand work without seeing the original brand. Produces a markdown source of truth
  plus an on-brand HTML page. Use when someone asks to "build a brand kit", "extract brand
  guidelines", "create a brand guide", "what's our brand DNA", or "set up brand". Reads the
  brand-product profile and the brand's live site. Requires brand-product-foundation.
---

# brand-kit

The operating procedure lives in the brain docs this package installs:

1. Read `/agent/brain/brand-kit/sop.md` for inputs, the kit structure, and the deliverables.
2. Read the brand-product profile for voice, positioning, and claims. If missing, route to
   `brand-product-foundation`.

## Key rules

- Pull visual-system values from the site's computed DOM styles, not raw stylesheets or guesses.
- Messaging respects the profile's claims guard (banned language, required disclaimers).
- Deliver both the markdown source of truth and an on-brand page; the kit is a source of truth
  other packages (ad-gen, landing pages, briefs) read.
