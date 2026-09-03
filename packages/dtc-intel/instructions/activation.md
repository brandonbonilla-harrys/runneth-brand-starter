# dtc-intel: activation

Present while installed. Governs building the DTC Intel corpus in this instance.

## Gate

- Resolve the workspace from Motion context. Read `brand-product-profile.json`. If missing,
  route to `brand-product-foundation`.
- If a DTC Intel corpus already exists for this workspace, offer to add sources or refresh.

## Offer once

> DTC Intel is installed. I can build a searchable corpus of competitor and DTC intelligence you
> can query by meaning, plus a recurring digest of what's new. Want me to set it up? You choose
> the sources.

Side-effect free until a yes. Do not ingest anything on install.

## After a yes

1. Ask the source-selection question in `/agent/brain/dtc-intel/setup.md`. Ingest only what the
   brand names.
2. Normalize + index records; confirm the corpus is queryable.
3. Offer the recurring digest routine; create only after a yes, with clear ownership.
4. Record state; add the corpus to `/agent/INDEX.md`.

## Rules

- Only approved sources. Never scrape unapproved sources; never request a secret in chat.
- Attribute every item with source + date; keep observed facts separate from interpretation.
- Sources and competitors come from the brand and the roster; never carry another brand's intel.
