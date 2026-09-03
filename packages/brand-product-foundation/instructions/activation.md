# brand-product-foundation: activation

Present in every conversation while installed. Governs the one-time brand + product setup. Once
the profile exists, stay quiet unless the person asks to review or update it.

## Check state first

Resolve the workspace only from the `Default workspace:` line in the Motion context. If a
`/agent/brain/<workspace>/brand-product-foundation/state.md` records `status: complete`, do not
offer setup. If it records `status: in-progress`, offer once to resume from its recorded phase.

## Offer once

If no state exists for this workspace, offer setup at most once per conversation:

> Before the other Runneth packages can be specific to this brand, I should learn your brand and
> your actual products. Setup is a guided interview (brand, every product, claims, naming,
> connections, KPI, delivery). It reads what's already connected, asks one question at a time,
> and writes a profile the other packages reuse so you never repeat yourself. Want to start?

The offer is side-effect free. Do not read connected accounts or write files before a yes.

## After a yes

1. Read `/agent/brain/brand-product-foundation/setup-interview.md` and follow it phase by phase,
   one question at a time. Pre-fill from Motion brand context and connected accounts; ask the
   person to confirm or correct rather than asking cold.
2. Save `state.md` after each phase so an interruption resumes cleanly.
3. At the close, write `/agent/brain/<workspace>/brand-product-profile.json` and the per-product
   `products/<id>.md` files exactly per
   `/agent/brain/brand-product-foundation/profile-schema.md`, add them to `/agent/INDEX.md`, and
   set `state.md` to `status: complete`.
4. Tell the person which installed downstream packages are now unlocked and offer to set up the
   first one.

## Rules

- This is the keystone. Other brand-starter packages read this profile; if they run before it
  exists, they should route the person here first.
- One question at a time. Never dump the whole interview at once.
- Confirm before writing the profile. Never invent products, claims, or connections.
- All output is scoped to `/agent/brain/<workspace>/` so multi-workspace setup stays additive.
- Never request or store secrets in this flow; confirm connections through the normal connect
  flows only.
