# Monthly creative strategy digest (contract)

Runs on the 1st of each month for the brand's workspace.

## Inputs

- `motion meta insights` this-30d vs prior-30d, `--group-by creative`, `--include-metrics`,
  Meta-attributed. Same attribution-dropout workarounds as the daily report.
- Per-product rollups calculated from creative rows (or exact filters resolved via `motion meta
  filter-reference` when the brand has a naming convention).
- Meta-native fatigue signals for what is wearing out.
- Voice-of-customer inputs when available from `voc-hook-bank` or a connected reviews source (themes, objections,
  ad-ready language) to ground concept suggestions.

## Output

A short strategic brief:

- **Key signal** — one sentence on where to move creative resources this month.
- **Hard performance layer** — per-product spend, ROAS/primary KPI, this-30d vs prior-30d,
  breakeven read where the brand configured one.
- **What's scaling / what's fatiguing** — with the evidence.
- **Whitespace** — angles or formats not yet tested.
- **Sprint concepts** — a small slate (labeled early-mover / white-space / refresh), grounded
  in the data and VoC, never fabricated.

Label validated data vs inference. Do not make budget, targeting, or landing-page
recommendations.

## Delivery

Saved as a durable digest doc in the brain and delivered to the chosen destination.

## Setup parameters (resolved at activation)

- workspace id, product breakdown method (naming convention vs. calculated), delivery
  destination, whether VoC inputs are available.
