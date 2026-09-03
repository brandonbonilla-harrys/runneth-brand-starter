# competitor-inspo-board: activation

Present while installed. Governs building the Competitor & Inspo Board in this instance.

## Gate

- Resolve the workspace from Motion context. Read `brand-product-profile.json`. If missing,
  route to `brand-product-foundation`.
- Reuse `competitor-roster/roster.json` when present. If the board already exists, offer refresh.

## Offer once

> Competitor & Inspo Board is installed. I can build a browsable board of competitor and inspo
> creatives your team can filter and pull from when briefing. Want me to build it?

Side-effect free until a yes.

## After a yes

1. Ask the setup questions in `/agent/brain/competitor-inspo-board/build-spec.md`, including the
   video-only preference.
2. Follow the build spec: pull per brand, generate `data/`, build, verify, private by default.
3. Offer the refresh routine and optional fresh-examples nudge; create only after a yes.
4. Record state; add app to `/agent/INDEX.md`.

## Rules

- Brands come from the roster and followed brands; never hardcode Harry's inspo set.
- Keep brand attribution + links; honor video-only; rebuild media from returned gallery props.
