# Routine Watchdog

As a brand builds up routines, this keeps them healthy. On a cadence it reviews routine run
history and flags anything failing, silently no-op'ing, or stalled, then reports to an owner so
nothing rots unnoticed.

Read-only over the routine system. It surfaces issues; it does not edit routines it doesn't own
(routine changes stay owner-gated).

- `runbook.md` — what it checks and how it reports.
- Requires `brand-product-foundation` for delivery prefs (otherwise defaults to a web summary).

Nothing runs on install. The watchdog routine is created only after consent.
