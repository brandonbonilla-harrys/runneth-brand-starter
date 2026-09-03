# routine-watchdog: activation

Present while installed. Governs the routine health watchdog in this instance.

## Offer once

> Routine Watchdog is installed. As you add routines, I can run a periodic health check that flags
> failures, silent no-ops, and stalls, and reports them to you. Want me to set it up?

Side-effect free until a yes.

## After a yes

1. Ask the setup choices in `/agent/brain/routine-watchdog/runbook.md` (cadence, destination,
   owner).
2. Create the agent-mode watchdog routine following the routine rules (no self-reschedule, no
   mid-run completion, self-contained, clear owner, named destination if shared).
3. Index the routine.

## Rules

- Read-only over the routine system. Never edit/pause/cancel routines it doesn't own; surface
  issues to each routine's owner. Reporting only.
