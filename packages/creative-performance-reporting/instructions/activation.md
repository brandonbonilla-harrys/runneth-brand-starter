# creative-performance-reporting: activation

This instruction is present in every conversation while this package is installed. It governs
onboarding only. Once the routines exist, they run on their own and this file stays quiet.

## Offer once

If this workspace has no `creative-performance-reporting/state.md` recording active routines,
you may offer setup at most once per conversation:

> Creative Performance Reporting is installed. I can set up a daily Meta performance report and
> a monthly creative strategy digest for this workspace. Setup will read this workspace's Meta
> performance data and create recurring routines you can edit or remove later. Want to set it up?

The offer is side-effect free. Do not read connected data, create routines, or write brain
files before an explicit yes.

## Resolve the workspace

Resolve the workspace only from the `Default workspace:` line in the Motion context for this
conversation. Never infer it from folders, memory, or another instance. If it is null, ask
which workspace before continuing.

## After a yes

1. Confirm: workspace, delivery destination (a new web conversation, this conversation, or a
   named Slack channel), the daily send time, and the monthly send day/time.
2. Confirm the primary KPI (offer `motion workspace-goal` if set, else spend) and an anomaly
   band for the daily guard.
3. Read the two SOP docs staged under `/agent/brain/creative-performance-reporting/`.
4. Create the two routines with `routine add`, following the SOP contracts and the routine
   authoring rules (both `--delivery` and `--prompt`; resolve contextual delivery words before
   authoring; do not depend on Slack search to rediscover a fixed destination).
5. Write `/agent/brain/creative-performance-reporting/state.md` with the workspace id, routine
   ids, and settings so setup is not offered again, and add both to `/agent/INDEX.md`.

## Notes

- Meta-attributed only. Do not introduce Northbeam unless the person explicitly asks and the
  workspace is configured for it.
- Apply the attribution/label-dropout workarounds described in the SOP docs.
- All state is scoped to this workspace so multi-workspace setup stays additive.
