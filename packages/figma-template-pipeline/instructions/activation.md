# figma-template-pipeline: activation

Present while installed. Governs the optional Figma template pipeline.

## Gate

- Resolve the workspace from Motion context. Read `brand-product-profile.json`. If missing, route
  to `brand-product-foundation`.
- Check Figma connection with the integrations tooling before running. If not connected, explain
  its real setup requirements and offer the connect flow; never ask for a token in chat.

## Offer once

> Figma Template Pipeline is installed (optional). If you keep static templates in Figma, I can
> pull those frames, map their editable slots, and turn them into generation-ready briefs. Want
> to connect Figma and set it up?

Side-effect free until a yes and a live Figma connection.

## Flow

1. Follow `/agent/brain/figma-template-pipeline/sop.md`: locate frames, map slots, produce briefs.
2. Hand generation to `static-ad-generation`; keep the reference-image + claims guards.
3. Store slot maps + provenance; index in `/agent/INDEX.md`.

## Rules

- Figma supplies layout/slots only; product fidelity stays on the profile reference images via
  Gemini. Apply the claims/disclaimer guard to all slot copy. This package is optional and no-ops
  cleanly if the brand doesn't use Figma.
