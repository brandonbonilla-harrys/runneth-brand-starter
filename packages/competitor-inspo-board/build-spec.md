# Competitor & Inspo Board build spec

Build fresh in the target instance. Populate from the roster and followed inspo brands.

## Prerequisites

- `brand-product-profile.json` present. `competitor-roster` recommended (reuse `roster.json`).

## Setup questions

1. Which brands feed the board (roster + followed brands by default; let them trim).
2. Video-only or all formats? (Respect a producer video-only preference if one is saved.)
3. How many creatives per brand and the recency window.
4. Refresh cadence.

## Data sources (Motion)

- `motion inspo unique-creatives --brand-id <id> --brand-names-by-id '{...}'` per brand, applying
  a `formats` filter when video-only, and status/active filters as requested.
- Saved inspo boards: `motion inspo boards` + `motion inspo board-items` when the team keeps them.
- Use the returned `creativeGallerySpecPatches` / gallery hints for renderable media; keep brand
  attribution and links.

## Data model (`data/`)

- `board.json` — creatives with brand, format, angle tags, media/thumbnail, link, saved date.
- `brands.json` — the brands feeding the board.

## Layout

- Gallery grid with filters (brand, format, angle). Each card shows the creative, brand, and a
  link out. A "saved by the team" section for items they pin.

## Build steps

1. `app create competitor-inspo-board`, scaffold. 2. Generate `data/`. 3. `app build`,
   `app verify`. Private by default.

## Refresh routine

- On cadence: re-pull per brand, refresh the board, flag notable new creatives. Optional daily
  fresh-examples nudge (video-only if set).

## Guards

- Keep brand attribution and links on every competitor creative. Video-only means no static in
  the board or nudge. Rebuild media from returned gallery props, don't hand-build media URLs.
