# Creative Component Dashboard build spec

Build fresh in the target instance. Do not port the Harry's app; the decode logic is entirely
driven by the brand's own naming convention.

## Prerequisites

- `brand-product-profile.json` present. Read `naming` from it.
- A naming convention exists in the profile. If `naming.hasConvention` is false, capture the token
  structure with the person before building (Brand & Product Foundation records it); do not
  build the dashboard on an assumed scheme.
- Meta connected.

## Setup questions

1. Confirm the token structure to decode (from the profile `naming`), and which tokens become
   dashboard dimensions (e.g. product, hook, format, angle, creator, iteration).
2. Reporting window (default last_30d) and primary metric for ranking components.
3. Minimum spend to include a component (use the workspace spend threshold if set).
4. Refresh cadence.

## Decode + data sources

- Pull ad-name-grain performance: `motion meta ads --grain adnames --include-metrics` for the
  window. Optionally `--grain ads` for row-level joins.
- Parse each ad name into tokens using the confirmed structure. Unparseable names go to an
  `UNKNOWN` bucket and are surfaced to the person for correction, never silently dropped.
- Aggregate metrics per token value and per token-pair (e.g. hook x product).
- Apply the attribution/label-dropout workarounds.

## Data model (`data/`)

- `components.json` — per dimension, per value: spend, primary metric, count, share.
- `pairs.json` — selected cross-dimension rollups (hook x product, format x angle).
- `ads.json` — decoded ad rows for drill-down.
- `unknown.json` — names that failed to decode, with the raw name and best-guess.

## Layout

- A dimension switcher (product, hook, format, angle, creator...). Ranked bar per value with the
  primary metric; drill into the ads behind a value. A cross-dimension heatmap. An UNKNOWN queue.
- State the scope on every view and whether the rollup was returned directly or calculated from
  the decoded rows.

## Build steps

1. `app create creative-component-dashboard`, scaffold.
2. Generate `data/` from the decode.
3. `app build`, `app verify`. Private by default.

## Refresh routine

- On cadence: re-pull ad-name performance, re-decode, regenerate `data/`, rebuild, and surface
  any new UNKNOWN names for correction.

## Guards

- Components are attribution buckets; do not call a component "better" without a returned
  outcome/rate metric and its direction. Respect the spend threshold for winner/cut language.
