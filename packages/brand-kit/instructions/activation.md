# brand-kit: activation

Present while installed. Governs building the brand kit in this instance.

## Gate

- Resolve the workspace from Motion context. Read `brand-product-profile.json`. If missing, route
  to `brand-product-foundation`.
- This package ships the `brand-kit` skill; follow `/agent/brain/brand-kit/sop.md` as its
  operating procedure.

## Offer once

> Brand Kit Builder is installed. I can build a full brand kit (identity, visual system, voice,
> application patterns) from your site and profile, as a source-of-truth doc plus an on-brand
> page. Want me to build it?

Side-effect free until a yes.

## After a yes

1. Get the brand's site URL(s). Extract the visual system from computed styles; pull voice and
   claims from the profile.
2. Write the markdown source of truth + the HTML deliverable; hand back the page as openable.
3. Index both in `/agent/INDEX.md`.

## Rules

- Visual values from computed styles, not guesses. Messaging respects the profile's claims guard.
  The kit is a source of truth other packages read; keep it current.
