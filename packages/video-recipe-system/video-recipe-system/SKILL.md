---
name: video-recipe-system
description: |
  Build reusable video recipes (hook + script structure + shot list) from the brand's own
  winning video ads, using the real spoken transcripts. Use when someone says "build a video
  recipe", "turn this winning video into a template", "what's the script structure here", "make a
  reusable hook/script from our top videos", or "give me a shot list from this ad". Pulls verbatim
  transcripts and keeps the verbatim words separate from the analysis. Reads the brand-product
  profile. Requires brand-product-foundation and Meta connected.
---

# video-recipe-system

The operating procedure lives in the brain docs this package installs:

1. Read `/agent/brain/video-recipe-system/sop.md` for building a recipe from real transcripts.
2. Read the brand-product profile for products/positioning. If missing, route to
   `brand-product-foundation`.

## Key rules

- Pull the actual spoken words with the transcript flow (`motion meta insights --include-transcript`)
  for the specific videos being analyzed. Never substitute summaries, ad names, or tags for the
  transcript.
- Keep verbatim quotes separate from interpretation; label what is observed vs inferred.
- A recipe is the reusable structure (hook type, script beats, shot list), not a copy of one ad.
