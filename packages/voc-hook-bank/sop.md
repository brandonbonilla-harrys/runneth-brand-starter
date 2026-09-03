# VoC Hook Bank SOP

Build a hook/angle bank from the brand's real customer voice.

## Prerequisites

- `brand-product-profile.json` present. A connected reviews platform (Okendo, Yotpo, etc.)
  and/or Meta ad comments. Confirm connections; never ask for a secret in chat.

## 1. Source the voice

- Reviews: pull from the connected reviews source for the in-scope products.
- Ad comments: `motion meta creative-comments --creative-asset-id <id>` for the brand's creatives.
  Respect the comment-coverage caveats (dark posts, cached totals) and never report an unavailable
  count as zero.

## 2. Extract into buckets

- Sort language into the seven VoC buckets: pain points, desires, failed solutions, objections,
  trigger moments, transformations, standout language. Keep the exact verbatim quote and its
  attribution (reviewer name + star rating, or comment platform + date) with every item.

## 3. Draft hooks

- For each strong bucket item, draft 1-2 ad-ready hooks that stay in the customer's own words.
  Tag each hook to product, persona, and bucket. Keep the source quote attached to the hook.
- Apply the product's `claims` guard: a hook that implies a banned/medical claim gets reworded or
  dropped.

## 4. Quantify recurring themes

- When a theme recurs (an objection, an unbundle ask, a repeated praise), report it as a percent
  of total for that product, state the denominator, and flag coverage gaps as directional.

## 5. Store

- Save the bank under `/agent/brain/<workspace>/voc-hook-bank/<product>.md`: hooks with their
  verbatim quote, attribution, bucket, persona, and claims status. Index in `/agent/INDEX.md`.

## Refresh

- Offer a periodic refresh that adds new hooks from fresh reviews/comments; create the routine
  only after a yes.

## Guards

- Every cited insight carries its verbatim quote + attribution. Never fabricate or paraphrase a
  quote as if verbatim. Claims guard applies to every drafted hook.
