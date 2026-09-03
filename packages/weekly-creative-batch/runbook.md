# Weekly Creative Batch runbook

Runs weekly. Agent-mode routine (image generation + fidelity grading are judgment work, not a
deterministic script). Each run:

## Prerequisites

- `brand-product-profile.json` present. `static-ad-generation` installed. `GEMINI_API_KEY`
  connected. Template library and coverage matrix improve selection but are not required.

## Setup choices (ask once)

1. Batch size (default 3-5 concepts/week).
2. Which products are in rotation (default: all in the profile).
3. Delivery destination for approval cards (from profile delivery prefs).
4. Whether to post a plan preview before generating, or go straight to approval cards. (Default:
   straight to cards; some teams don't want the plan narrated.)
5. Day/time to run.

## Each run

1. **Score + select.** Combine coverage whitespace (untested angle x product cells) with recent
   performance (reformat proven winners into new formats). Pick the batch. Apply attribution/label
   workarounds on any performance pull.
2. **Generate.** For each concept, run the `static-ad-generation` SOP: reference-images-only
   Gemini prompt, claims/disclaimer guard from the product profile, mandatory 4x5 aspect
   enforcement, fidelity review.
3. **Brief + deliver.** Produce the HTML brief per static and deliver approval cards to the chosen
   destination (labeled links, no raw paths; follow the brand's Slack format prefs).
4. **Log.** Update the asset ledger and learning notes. Surface any UNKNOWN/low-fidelity items for
   correction rather than shipping them.

## Routine rules (must follow)

- Agent-mode routine. Do not force script mode.
- No self-reschedule and no completing the routine mid-run; let the scheduler own the cadence.
- Do not depend on searching Slack inside the run, and do not rely on the routine remembering its
  own prior Slack post. Any needed context must be self-contained in the prompt.
- Clear owner. If it posts to a shared channel, name the destination in the setup confirmation.

## Guards

- Every static passes the claims/disclaimer guard and 4x5 enforcement. Never present a
  low-fidelity render as approval-ready. Reference-images-only; no product descriptions or
  negative prompts.
