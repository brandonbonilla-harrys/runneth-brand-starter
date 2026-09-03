# Routine Watchdog runbook

Periodic health check over the brand's routines. Read-only.

## Setup choices (ask once)

1. Cadence (default daily or weekly).
2. Where the health report goes (a web conversation or a named channel).
3. Who the owner/recipient is.

## Each run

1. `routine list` for the inventory; `routine history --id <id>` for recent runs of each active
   routine.
2. Flag: runs that errored, routines that produced no output when they should have, routines that
   haven't run when their schedule says they should, and any routine paused unexpectedly.
3. For each flag, include the routine name, owner (resolve from the routine record), last run,
   and the symptom. Do not attempt a fix.
4. Deliver a compact health summary. If all green, a one-line all-clear.

## Routine rules

- Agent-mode routine. No self-reschedule, no mid-run completion, no Slack-search dependency,
  self-contained prompt, clear owner, named destination if shared.

## Guards

- Read-only. Never edit, pause, resume, cancel, or restructure another routine; surface issues to
  the routine's owner and let them decide. Reporting only.
