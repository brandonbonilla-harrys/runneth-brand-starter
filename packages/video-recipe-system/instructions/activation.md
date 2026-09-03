# video-recipe-system: activation

Present while installed. Governs building/using video recipes in this instance.

## Gate

- Resolve the workspace from Motion context. Read `brand-product-profile.json`. If missing, route
  to `brand-product-foundation`.

## Offer once

> Video Recipe System is installed. I can turn your winning video ads into reusable recipes (hook
> + script structure + shot list) your producers can brief new cuts from. Want me to build them?

Side-effect free until a yes.

## Flow

1. Follow `/agent/brain/video-recipe-system/sop.md`: select winners, pull transcripts, extract
   recipes, store, index.
2. When briefing a new cut, fill a recipe from the profile and keep the claims/disclaimer guard.
3. Offer a periodic refresh routine; create only after a yes.

## Rules

- Recipes come from real transcripts (`--include-transcript`); never invent lines. Keep verbatim
  separate from analysis. Re-check claims against the product profile before any new cut ships.
- Focus products and delivery come from the profile; never carry Harry's products or scripts.
