# Static Ad Generation

The single SOP for generating a static image ad for any of the brand's products. It keeps the
proven mechanics of the Harry's system (reference-images-only prompting, strict product fidelity,
a claims guard, aspect enforcement, an HTML brief) but drives every product-specific input from
the brand-product profile, so it works for a brand whose products are nothing like Harry's.

Pinned to the **Gemini reference-image flow** as the default engine.

- `sop.md` — the step-by-step: context load, template/hook selection, reference-images-only
  prompt build, claims/placeholder guard, generation, aspect enforcement, fidelity review, asset
  ID + naming, HTML brief, ledger/learning updates, delivery.
- Requires `brand-product-foundation` (reads products, reference images, claims, disclaimers).

Nothing runs on install. Generation happens only when the person asks for a static.
