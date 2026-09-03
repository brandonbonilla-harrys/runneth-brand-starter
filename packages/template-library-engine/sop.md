# Template Library Engine SOP

Build and grow the brand's static-ad template pool. Templates are structure/layout only
(reference-image compatible), never product-specific art.

## Prerequisites

- `brand-product-profile.json` present. `GEMINI_API_KEY` for vision classification + minting.

## 1. Harvest

- Pull competitor/inspo statics via Inspo (`motion inspo unique-creatives` with an image format
  filter, across the roster + followed brands). Save candidates to a working set with attribution.

## 2. Vision-classify

- For each candidate, classify layout family, composition, text placement, mechanic (comparison,
  before/after, feature-callout, UGC-style, editorial, etc.) using Gemini vision. Record tags.

## 3. Dedupe

- Collapse near-duplicates by layout family + mechanic so the pool stays diverse, not repetitive.

## 4. Mint net-new IP templates

- Turn distinct, high-quality patterns into **reference-only templates**: a layout/structure
  description + a clean template reference image that carries no competitor branding and no
  product. The template describes where product, copy, and proof go, not what the product is.
- Reject anything that is just "product on a flat fill + text."

## 5. Store + version

- Save templates under `/agent/brain/<workspace>/templates/statics/<template-id>/` with the
  reference image, the structure notes, mechanic tags, and provenance. Index them in
  `/agent/INDEX.md` so `static-ad-generation` can pick one.
- Keep the pool refreshable: new harvests add or version templates without clobbering existing ones.

## Refresh

- Offer a recurring harvest (default weekly) that proposes net-new templates for approval before
  they enter the pool. Create the routine only after a yes.

## Guards

- Templates are layout IP, not copied competitor creatives; strip all competitor branding and
  product art. Keep provenance for reference. Everything here stays reference-image compatible so
  it plugs straight into the Gemini static flow.
