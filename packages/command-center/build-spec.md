# Command Center build spec

Build this fresh in the target instance after the brand-product profile exists. Do not port the
Harry's app source; scaffold a new app and generate data from this brand's Motion account.

## Prerequisites

- `brand-product-profile.json` present for the workspace. If missing, route the person to
  `brand-product-foundation` first.
- Meta connected for the workspace.

## Setup questions (beyond the profile)

1. Which products get their own tab? (default: all products in the profile)
2. Reporting window for the main view (default: last_30d, trend vs prior period).
3. Fatigue emphasis: Meta-native fatigue only, or Meta-native plus spend/frequency context?
4. Refresh cadence (default: daily) and whether to post a change summary anywhere.

## Data sources (Motion)

- Per product: `motion meta insights --group-by creative --include-metrics` filtered to that
  product. Resolve the product filter from the profile's naming convention via `motion meta
  filter-reference`; if the brand has no convention, calculate the split client-side from
  creative rows and label it directional.
- Fatigue: `motion meta fatigued-ads` / `motion meta fatigued-adsets` (Meta-native; never infer
  fatigue from frequency/CTR).
- Benchmark: `motion benchmark-compare` for testing volume, hit rate, winner mix.
- Apply the Meta -> Motion attribution/label dropout workarounds on every pull.

## Data model (`data/` JSON files, one set per product)

- `<PRODUCT>.json` — creative rows with metrics for the window.
- `<PRODUCT>-clusters.json` — creatives grouped by shared DNA (format, angle, hook family) with
  per-cluster spend and outcome.
- `<PRODUCT>-trajectory.json` — per-creative or per-cluster movement across sub-periods.
- `<PRODUCT>-forecast.json` — simple forward read from the trajectory (labeled projection, never
  presented as Motion source data).
- `benchmark.json`, `coverage.json`, `actions.json`, `creative-context.json` — shared views.

## Layout

- Product tabs. Each tab: KPI strip, scaling vs fatiguing, cluster grid, trajectory chart,
  forecast callout, and the action list. A benchmark tab and an account-wide action tab.
- Every section states its scope (workspace, window, attribution, grouping, metric) and whether
  the view was returned directly or calculated.

## Build steps

1. `app create command-center` (or a brand-suffixed name), scaffold Astro flat app.
2. Generate the `data/` files from the Motion pulls above.
3. `app build` then `app verify`. Keep it private by default.
4. Hand back the openable app.

## Refresh routine

- Daily agent routine: re-pull, regenerate `data/`, rebuild. Optional one-line change summary to
  the chosen destination. Owner is the person who sets it up.

## Guards

- Never label a creative efficient/winning/scale-worthy from spend or spend-per-creative alone;
  require a returned outcome/rate metric and its documented direction.
- Forecasts and clusters are derived; label them, keep sparse series sparse.
