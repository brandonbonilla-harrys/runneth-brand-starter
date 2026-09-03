# weekly-creative-batch: activation

Present while installed. Governs the weekly static batch in this instance.

## Gate

- Resolve the workspace from Motion context. Read `brand-product-profile.json`. If missing, route
  to `brand-product-foundation`.
- Confirm `static-ad-generation` is installed and `GEMINI_API_KEY` is connected. If not, set those
  up first.

## Offer once

> Weekly Creative Batch is installed. I can run a weekly batch that picks what statics to make
> from your coverage gaps and recent winners, generates them, and sends you approval cards. Want
> me to set up the routine?

Side-effect free until a yes. Do not create the routine on install.

## After a yes

1. Ask the setup choices in `/agent/brain/weekly-creative-batch/runbook.md` (batch size, products,
   destination, preview or not, day/time).
2. Create the weekly agent-mode routine following the routine rules in the runbook (no
   self-reschedule, no mid-run completion, no Slack-search dependency, self-contained prompt,
   clear owner, named destination if shared).
3. Record state; index the routine/output.

## Rules

- Generation follows the `static-ad-generation` SOP: reference-images-only Gemini flow, claims
  guard, mandatory 4x5. Products/claims/delivery come from the profile; never carry Harry's
  products, GADV scheme, p-code naming, or the Harry's "no Friday preview" preference. Preview
  behavior is a per-brand setup choice.
