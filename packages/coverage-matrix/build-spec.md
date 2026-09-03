# Coverage & Whitespace Matrix build spec

Build fresh in the target instance. Axes and cells are driven by the brand-product profile.

## Prerequisites

- `brand-product-profile.json` present (products, personas). Meta connected.
- An angle list: reuse the profile's personas/benefits/objections to seed messaging angles, or
  ask the person to confirm/extend the angle list at setup.

## Setup questions

1. Confirm the angle axis (seed from profile benefits/objections/personas; let them edit).
2. Second axis: products only, or products x format (video/image/carousel)?
3. What counts as "tested" (default: at least 1 creative with any spend; optionally a spend
   threshold for "meaningfully tested").
4. Reporting window and primary metric for the performance shown in tested cells.
5. Refresh cadence.

## Determining coverage

- Pull creatives: `motion meta insights --group-by creative --include-metrics` for the window.
- Tag each creative to an angle using glossary categories (messaging angle / hook tactic) via
  `--glossary-category`, and to a product via the naming convention or client-side split. Map
  tagged creatives into the angle x product grid.
- A cell is tested if it has qualifying creatives; otherwise it is whitespace. Apply the spend
  threshold if the person chose "meaningfully tested". Apply attribution/label-dropout workarounds.

## Data model (`data/`)

- `matrix.json` — cells with state (untested / tested / meaningfully-tested), creative count,
  spend, and primary metric.
- `angles.json`, `products.json` — axis definitions.
- `cell-ads.json` — the creatives behind each tested cell for drill-down.

## Layout

- The grid: color by state, number by performance where tested. Click a cell to see its
  creatives or, for whitespace, a prompt to brief that combination. State scope on the view and
  that angle/product tagging was calculated from the creatives pulled.

## Build steps

1. `app create coverage-matrix`, scaffold. 2. Generate `data/`. 3. `app build`, `app verify`.
   Private by default.

## Refresh routine

- On cadence: re-pull, re-tag, regenerate the matrix, rebuild; optionally flag newly-filled or
  still-empty high-value cells.

## Guards

- Tagging is calculated from returned creatives and their glossary tags; call it directional and
  do not present it as a Motion-returned grouping. Do not call a tested cell a winner from spend
  alone.
