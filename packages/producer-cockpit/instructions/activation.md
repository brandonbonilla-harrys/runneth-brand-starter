# producer-cockpit: activation

Present while installed. Governs building the Producer Cockpit in this instance.

## Gate

- Resolve the workspace from Motion context. Read `brand-product-profile.json`. If missing,
  route to `brand-product-foundation`.
- If the cockpit already exists for this workspace, offer to refresh instead of duplicating.

## Offer once

> Producer Cockpit is installed. I can build a producer-facing app with hook and script
> teardowns of your top video ads (real transcripts), your recent work, and a live feed of
> competitor and inspo videos to borrow from. Want me to build it?

Side-effect free until a yes.

## After a yes

1. Ask the setup questions in `/agent/brain/producer-cockpit/build-spec.md` (including the
   video-only inspo preference).
2. Follow the build spec: pull top ads + transcripts + inspo, generate `data/`, build, verify,
   private by default.
3. Offer the refresh routine and optional daily fresh-examples nudge; create only after a yes.
4. Record state; add app to `/agent/INDEX.md`.

## Rules

- Transcripts only via `--include-transcript`; never invent spoken content. Keep verbatim
  transcript separate from analysis.
- Honor a video-only inspo preference across the app and any nudge routine.
- Read focus products and delivery from the profile; never hardcode Harry's products.
