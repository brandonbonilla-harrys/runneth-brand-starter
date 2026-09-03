# Template Library Engine

Builds and maintains the brand's own library of static-ad templates: it harvests competitor and
inspo statics, vision-classifies and dedupes them, and mints genuinely net-new reference-only IP
templates the brand can generate against. It's the uniqueness bar that keeps generated statics
from being generic "product on a plain background + text."

Feeds `static-ad-generation` (which picks a template to fill). Reads the brand-product profile.

- `sop.md` — harvest, classify, dedupe, mint, and how templates are stored/versioned.
- Requires `brand-product-foundation`; works best alongside `competitor-inspo-board`.

Nothing runs on install. Harvesting/minting happens only after an explicit yes.
