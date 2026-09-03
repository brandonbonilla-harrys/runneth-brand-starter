# Video Recipe System SOP

Build reusable video recipes from the brand's winning videos.

## Prerequisites

- `brand-product-profile.json` present. Meta connected.

## 1. Select winners

- Pull top video ads for the focus products/window: `motion meta insights --group-by creative
  --include-metrics` filtered to video, ranked by the primary metric. Apply attribution/label
  workarounds.

## 2. Pull the words

- For the selected creative asset ids, pull transcripts with `motion meta insights
  --creative-asset-id <id> --include-transcript` and the hook/messaging summary sections. Keep the
  performance window and the transcript lookup window separate.

## 3. Extract the recipe

- For each winner, capture: the hook (verbatim opening line), the script structure (beats:
  hook -> problem -> proof -> payoff -> CTA, or whatever the ad actually does), pacing, and a
  shot list inferred from the structure. Mark which product claims it uses so briefs stay
  claims-safe.
- Label verbatim transcript separately from the structural analysis.

## 4. Store

- Save recipes under `/agent/brain/<workspace>/video-recipes/<recipe-id>.md`: hook, structure,
  shot list, claims used, source ad + metrics. Index in `/agent/INDEX.md`.

## 5. Reuse

- When briefing a new cut, pick a recipe and fill it for the target product/persona from the
  profile, keeping the claims/disclaimer guard. Hand to the briefing skill or producer.

## Refresh

- Offer a periodic recipe refresh from new winners; create the routine only after a yes.

## Guards

- Recipes are built from real transcripts; never fabricate spoken lines. Keep verbatim separate
  from analysis. Claims used in a recipe must be re-checked against the product's profile claims
  before any new cut ships.
