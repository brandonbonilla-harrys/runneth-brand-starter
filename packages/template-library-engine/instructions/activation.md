# template-library-engine: activation

Present while installed. Governs building/growing the static template library in this instance.

## Gate

- Resolve the workspace from Motion context. Read `brand-product-profile.json`. If missing, route
  to `brand-product-foundation`.
- Confirm `GEMINI_API_KEY` for vision classification/minting; point to connect flow if missing.

## Offer once

> Template Library Engine is installed. I can harvest competitor and inspo statics, classify and
> dedupe them, and mint net-new reference-only templates your static generator can use. Want me
> to build your template pool?

Side-effect free until a yes.

## When to run

- Trigger on requests to mint a template, build/refresh the template library, or harvest inspo
  formats. Follow `/agent/brain/template-library-engine/sop.md`.

## After the pool exists

- Offer a recurring harvest routine (default weekly) that proposes net-new templates for approval;
  create only after a yes, with clear ownership. Index templates in `/agent/INDEX.md`.

## Rules

- Templates are layout IP only: strip competitor branding and product art; keep provenance.
- Reference-image compatible so they plug into the Gemini static flow. No "flat fill + text."
