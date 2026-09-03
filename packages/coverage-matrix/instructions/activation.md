# coverage-matrix: activation

Present while installed. Governs building the Coverage & Whitespace Matrix in this instance.

## Gate

- Resolve the workspace from Motion context. Read `brand-product-profile.json`. If missing,
  route to `brand-product-foundation`.
- If the matrix already exists for this workspace, offer to refresh instead of duplicating.

## Offer once

> Coverage & Whitespace Matrix is installed. I can build a grid of your messaging angles by
> product showing what you've tested versus the whitespace you haven't, with performance where
> you have. Want me to build it?

Side-effect free until a yes.

## After a yes

1. Ask the setup questions in `/agent/brain/coverage-matrix/build-spec.md`, seeding the angle
   axis from the profile's benefits/objections/personas and letting the person edit it.
2. Follow the build spec: pull + tag creatives, generate `data/`, build, verify, private default.
3. Offer the refresh routine; create only after a yes.
4. Record state; add app to `/agent/INDEX.md`.

## Rules

- Angles, products, and personas come from the profile; never hardcode Harry's angles.
- Tagging is calculated and directional; apply attribution/label-dropout workarounds and the
  effectiveness-claim guard.
