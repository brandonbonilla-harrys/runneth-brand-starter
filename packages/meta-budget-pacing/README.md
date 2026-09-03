# Meta Budget Pacing

A daily read on how the brand's Meta spend is pacing against plan: spend to date, run-rate, pace
vs the monthly target, and any delivery anomalies (a campaign stalled, a spike, a stripped-label
day). It reports, it does not change budgets.

Reads the brand-product profile for the spend target and delivery prefs. The Meta -> Motion
attribution/label-dropout workarounds are built in so a null-label day is never mis-read as a $0
stall.

- `runbook.md` — the daily sequence, the anomaly checks, and delivery.
- Requires `brand-product-foundation`; Meta connected.

Nothing runs on install. The daily routine is created only after consent, with an owner.
