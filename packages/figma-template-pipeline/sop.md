# Figma Template Pipeline SOP

Connect Figma template frames to the brand's generation flow.

## Prerequisites

- `brand-product-profile.json` present.
- Figma connected for the workspace (Pipedream `figma` app). Confirm before running; never ask
  for a Figma token in chat.

## 1. Locate frames

- Ask for the Figma file/URL and the page or frame set that holds the templates.
- Pull the frames and their layer structure via the connected Figma app.

## 2. Map slots

- For each template frame, identify editable slots: product image slot, headline, subhead, proof,
  CTA, badge, etc. Record the slot map for the template.
- Link the frame to a template id in the brand's template library when one matches, or register it
  as a new template entry.

## 3. Produce generation-ready briefs

- For a chosen product + hook, fill the slot map from the profile (product reference image, copy,
  claims-safe headline/proof) and hand off to `static-ad-generation`. Keep the reference-image
  and claims guards intact; Figma supplies structure, not product art.

## 4. Store

- Save slot maps and frame provenance under
  `/agent/brain/<workspace>/templates/figma/<template-id>/`. Index in `/agent/INDEX.md`.

## Guards

- Figma provides layout/slots only. Product fidelity still comes from the profile's reference
  images through the Gemini flow. Apply the claims/disclaimer guard to all copy that lands in a slot.
