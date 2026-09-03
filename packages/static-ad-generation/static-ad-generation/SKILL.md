---
name: static-ad-generation
description: |
  Generate a static image ad for any of the brand's products using the reference-image flow
  (Gemini image generation), with product fidelity carried by the product's own reference images,
  the product's allowed/banned claims and disclaimers enforced as a hard gate, aspect-ratio
  enforcement, fidelity review, asset naming, and an HTML brief. Use when someone says "generate a
  static", "make a static ad", "create a static", "new static for <product>", "spin up a static",
  or "regenerate this static". All product specifics (reference images, claims, disclaimers,
  naming) are read from the brand-product profile; nothing is hardcoded. Requires
  brand-product-foundation and a connected image-generation key.
---

# static-ad-generation

This skill's operating procedure lives in the brain docs this package installs. Follow them in order:

1. Read `/agent/brain/static-ad-generation/sop.md` for the full step-by-step SOP.
2. Read the brand's `brand-product-profile.json` and the featured product's record for reference
   images, allowed/banned claims, disclaimers, and naming. If the profile is missing, route the
   person to `brand-product-foundation` first.

## Hard rules (also in the SOP)

- Reference images only. Do not describe the product in the prompt and do not include a
  negative-prompt list; fidelity comes from the attached reference images.
- The product's `claims` guard is a hard gate: no banned or medical-style copy; required
  disclaimers applied.
- Enforce the brand's chosen aspect ratio on every output.
- Review fidelity before calling anything approval-ready; deliver the HTML brief and update the
  asset ledger.
