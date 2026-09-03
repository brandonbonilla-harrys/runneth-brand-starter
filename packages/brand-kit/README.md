# Brand Kit Builder

Builds a complete brand kit for the brand: identity, visual system (from computed site styles),
voice and messaging, application patterns, and anti-patterns, dense enough that another agent can
produce on-brand work without ever seeing the original brand. Grounded in the brand-product
profile and the brand's live site.

Produces a markdown source of truth plus an on-brand HTML deliverable styled in the brand's own
system.

- `sop.md` — inputs, extraction, the kit structure, and the deliverables.
- Requires `brand-product-foundation`. This package ships the `brand-kit` skill; `sop.md` is its
  operating procedure.

Nothing runs on install. The kit is built only after an explicit yes.
