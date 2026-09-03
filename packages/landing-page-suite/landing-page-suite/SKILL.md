---
name: landing-page-suite
description: |
  The landing-page workflow for the brand: deep-extract a page into a structured spec, CRO-audit
  it against the ads pointing at it, generate a prioritized A/B test backlog, and build new pages.
  Use when someone asks to "summarize this landing page", "extract this URL", "CRO review",
  "optimize this landing page", "what should we A/B test", "experiment backlog", or "build a
  landing page". Grounded in the brand-product profile and brand kit. Requires
  brand-product-foundation.
---

# landing-page-suite

The operating procedure lives in the brain docs this package installs:

1. Read `/agent/brain/landing-page-suite/guide.md` for the four chained capabilities (summarize,
   optimize, experiments, build) and when to use each.
2. Read the brand-product profile for voice and claims, and the brand kit for the visual system.
   If the profile is missing, route to `brand-product-foundation`.

## Key rules

- Always summarize the page fresh before an audit or an experiment backlog; never run off a stale
  summary.
- Variant and page copy respects the profile's claims guard and stays on-brand (brand kit).
- Read prior audit history so shipped fixes aren't re-suggested. Do not make budget, targeting, or
  campaign-structure recommendations; stay on page and message.
