# Brand Kit Builder SOP

Build the brand's kit. If the official `brand-kit` skill is installed in this instance, use it;
this SOP is the fallback and the profile-grounding layer.

## Prerequisites

- `brand-product-profile.json` present (brand voice, positioning, competitors, products).

## Inputs

1. The brand's primary site/landing URL(s). Extract the visual system from **computed DOM styles**
   (not raw stylesheets): color roles, type scale, spacing, radii, buttons, imagery treatment.
2. The profile's voice, positioning, and product framing for the messaging system.

## Kit structure

- Identity: mission/positioning, personality, do/don't tone.
- Visual system: color roles + hex, type scale, spacing/radius tokens, button/component patterns,
  imagery style.
- Voice & messaging: value props, proof, product-level messaging, banned/required language pulled
  from the profile's `claims`.
- Application patterns: how the system shows up on ads, pages, social, email.
- Anti-patterns: what to never do.

## Deliverables

- `/agent/brain/<workspace>/brand-kit/brand-kit.md` — the markdown source of truth.
- An HTML deliverable styled in the brand's own system, handed back as an openable page.
- Index both in `/agent/INDEX.md`.

## Guards

- Visual values come from computed styles, not guesses. Messaging respects the profile's claims
  guard. Keep it a source of truth other packages (ad-gen, LP, briefs) can read.
