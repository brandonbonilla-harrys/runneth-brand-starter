# competitor-roster: activation

Present while installed. Governs building the competitor roster in this instance.

## Gate

- Resolve the workspace from Motion context. Read `brand-product-profile.json`. If missing,
  route to `brand-product-foundation`.
- If a roster already exists for this workspace, offer to refresh or edit it rather than rebuild.

## Offer once

> Competitor Roster is installed. I can map your competitors into a tracked roster and give you a
> weekly read on what they're running. Want me to set it up?

Side-effect free until a yes.

## After a yes

1. Ask the source-preference question in `/agent/brain/competitor-roster/setup.md` (interview
   names / followed brands / both; default both).
2. Resolve and confirm each brand's identity, save `roster.json`, and surface anything
   unresolved for correction.
3. Produce the first weekly read; offer the weekly refresh routine and create only after a yes,
   with clear ownership.
4. Record state; add roster + any app to `/agent/INDEX.md`.

## Rules

- Competitors come from the profile and followed brands; never hardcode Harry's competitors.
- Confirm fuzzy brand matches before locking ids. `impressionRank` is a signal, not truth.
