# Producer Cockpit build spec

Build fresh in the target instance. Populate from the brand's own creatives and competitor/inspo.

## Prerequisites

- `brand-product-profile.json` present. Meta connected. Competitor/inspo brands followed in the
  workspace help the inspo feed but are not required.

## Setup questions

1. Which products or territories the producer focuses on (default: all in the profile).
2. How many top ads to teardown per refresh (default: top 10-15 by spend in the window).
3. Video-only inspo, or include static? (Ask; some producers want video only.)
4. Refresh cadence and whether to send a daily fresh-examples nudge.

## Data sources (Motion)

- Top video ads: `motion meta insights --group-by creative --include-metrics` filtered to video,
  ranked by the window's primary metric. Then pull transcripts for the selected creative asset
  ids with `motion meta insights --creative-asset-id <id> --include-transcript` and the hook /
  messaging summary sections. Keep performance window and transcript lookup window separate.
- Recent work: latest launched creatives for the focus products.
- Competitor/inspo: `motion inspo brands` + `motion inspo unique-creatives` (respect a video-only
  preference), and saved inspo boards via `motion inspo boards` / `board-items` when present.
- Apply attribution/label-dropout workarounds on performance pulls.

## Data model (`data/`)

- `teardowns.json` — per top ad: hook line, transcript, script-structure notes, metrics, thumb.
- `recent.json` — recent creatives.
- `inspo.json` / `competitors.json` — competitor + inspo examples (video-forward), with source
  attribution and links.
- `summary.json` — the week's read for the producer.

## Layout

- Teardown gallery (thumb + hook + transcript + structure notes + metrics). Recent-work strip.
  Inspo feed filtered to the producer's format preference. Every ad reference shows the creative
  and links out; competitor items keep brand attribution.

## Build steps

1. `app create producer-cockpit`, scaffold.
2. Generate `data/`. `app build`, `app verify`. Private by default.

## Refresh routine

- On cadence: refresh top ads + transcripts, recent work, and inspo. Optional daily
  fresh-examples nudge to the producer's destination (video-only if they set that).

## Guards

- Transcripts must come from `--include-transcript`; never fabricate spoken words from summaries
  or thumbnails. Label teardown structure notes as analysis, separate from the verbatim transcript.
