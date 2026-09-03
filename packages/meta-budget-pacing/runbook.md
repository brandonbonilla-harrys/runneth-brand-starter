# Meta Budget Pacing runbook

Daily. Reports pacing; never recommends or changes budgets, targeting, or structure.

## Prerequisites

- `brand-product-profile.json` present (spend target, delivery prefs). Meta connected.

## Setup choices (ask once)

1. The pacing target (monthly budget or daily target). Use the profile if set.
2. Split by product/campaign or account-wide.
3. Delivery destination and time.

## Each run

1. Pull spend for the period: broad `motion meta insights` (or `motion meta ads --grain ads` when
   labels are needed). Apply the attribution/label-dropout workarounds: broad pull + client-side
   split rather than a name filter, widen `--limit` before concluding a null window, ad-grain
   fallback when >~20% of rows have null names, and a freshness/sync-cutoff check so a null-label
   read is never reported as a $0 stall.
2. Compute spend to date, run-rate, and pace vs target (ahead/behind, projected end-of-period).
3. Anomaly checks: a campaign that dropped to ~0, an unusual spike, or a degraded-label day. Flag
   with the recovery path used and quantify the null-row share; hold any delta whose baseline day
   is itself degraded.
4. Deliver a compact pacing summary to the chosen destination (bold header for Slack; follow the
   brand's format prefs).

## Routine rules

- Agent-mode routine. No self-reschedule, no mid-run completion, no Slack-search dependency,
  self-contained prompt, clear owner, named destination if shared.

## Guards

- Reporting only. State scope (workspace, window, attribution, grouping) on every number. Never
  make budget, targeting, landing-page, or campaign-structure recommendations. Meta-attributed.
