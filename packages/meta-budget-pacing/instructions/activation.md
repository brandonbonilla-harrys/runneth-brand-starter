# meta-budget-pacing: activation

Present while installed. Governs the daily pacing report in this instance.

## Gate

- Resolve the workspace from Motion context. Read `brand-product-profile.json`. If missing, route
  to `brand-product-foundation`. Meta must be connected.

## Offer once

> Meta Budget Pacing is installed. I can give you a daily read on how your Meta spend is pacing
> against plan, with delivery-anomaly flags. Want me to set up the daily report?

Side-effect free until a yes.

## After a yes

1. Ask the setup choices in `/agent/brain/meta-budget-pacing/runbook.md`.
2. Create the daily agent-mode routine following the routine rules (no self-reschedule, no mid-run
   completion, self-contained, clear owner, named destination if shared).
3. Index the routine/output.

## Rules

- Reporting only; never recommend or change budgets/targeting/structure. Apply the
  attribution/label-dropout workarounds; never mis-read a null-label day as a $0 stall. Target and
  delivery come from the profile.
