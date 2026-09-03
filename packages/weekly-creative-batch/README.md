# Weekly Creative Batch

A recurring weekly batch that decides what statics to make, generates them through the Gemini
static flow, and delivers approval cards. It scores coverage gaps and recent performance to pick
concepts, then runs the same SOP as `static-ad-generation` for each.

Reads the brand-product profile, the template library, and the coverage matrix. The generation
step follows the reference-images-only Gemini flow with the claims guard and aspect enforcement.

- `runbook.md` — the weekly sequence: score, select, generate, deliver, log.
- Requires `brand-product-foundation` and `static-ad-generation`; better with
  `template-library-engine` and `coverage-matrix`.

Nothing runs on install. The weekly routine is created only after explicit consent, with an owner.
