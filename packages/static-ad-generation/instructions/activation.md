# static-ad-generation: activation

Present while installed. Governs static ad generation in this instance.

## Gate

- Resolve the workspace from Motion context. Read `brand-product-profile.json`. If missing, route
  to `brand-product-foundation` before generating.
- Confirm the target product has reference images at its profile `referenceImages` location. If a
  product has no reference set, tell the person it must be added before fidelity generation; treat
  it as concept-only until then.
- Confirm `GEMINI_API_KEY` is connected. If not, point to the connect/secret flow; never ask for
  a key in chat.

## When to run

- Trigger on requests to generate/make/create/regenerate a static ad. This SOP is the manual and
  ad-hoc path; a weekly batch has its own package.

## Flow

1. Follow `/agent/brain/static-ad-generation/sop.md` end to end.
2. Enforce the claims/disclaimer guard from the product's profile `claims` and the mandatory 4x5
   aspect step.
3. Deliver the HTML brief as an openable link per the brand's delivery prefs.

## Rules

- Reference-images-only prompting; never describe the product or add a negative prompt.
- All product specifics (reference images, claims, disclaimers, naming) come from the profile;
  never carry Harry's products, GADV scheme, or p-code naming into another brand.
- Gemini reference-image flow is the pinned engine. Aspect enforcement via ffmpeg is mandatory.
