# Daily performance report (contract)

Runs each morning on the brand's default workspace unless another workspace was named at setup.

## Data pull

- `motion meta insights` for the workspace, `--date-range last_30d`, `--group-by creative`,
  `--include-metrics`. Also pull a short trailing window (`last_7d`) for movers.
- Meta-attributed only. Do not request or reference Northbeam unless the brand explicitly
  configured it at setup.
- Apply the Meta -> Motion attribution/label dropout workarounds: pull broad and split
  client-side rather than filtering by campaign name (a name filter drops null-label rows and
  can read as a false $0); widen `--limit` before concluding a window is empty; fall back to
  `motion meta ads --grain ads` when a large share of creative-grain rows have null names; and
  run a freshness/sync-cutoff check so a null-label read is never reported as a $0 stall.

## Report body

- Total spend, day-over-day delta, trailing-4-day trend.
- Top movers up and down by spend and by the workspace's primary KPI (from `motion
  workspace-goal` if set, else spend).
- Anomaly guard: flag delivery/spend swings beyond a configured band.
- Fatigue guard: for high-spend ads, surface Meta-native fatigue via `motion meta
  fatigued-ads` / `motion meta fatigued-adsets`; do not infer fatigue from frequency or CTR.
- Every number carries its scope in plain language: workspace, platform, date window,
  attribution, grouping, metric key, and whether it was returned directly or calculated.

## Delivery

- One-line headline to the channel root; full per-section detail in the thread (Slack), or the
  full report in the web conversation.
- Bold the header line on Slack deliveries.

## Setup parameters (resolved at activation)

- workspace id, delivery destination, send time, anomaly band, primary KPI.
