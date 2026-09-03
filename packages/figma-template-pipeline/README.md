# Figma Template Pipeline

Optional. For brands that keep their static templates in Figma, this connects those frames to the
generation flow: it pulls template frames from Figma, maps each frame's editable slots (product,
headline, proof, CTA) to the brand's product and copy, and produces generation-ready briefs.

Reads the brand-product profile. Requires a Figma connection. This is a convenience layer on top
of `template-library-engine` and `static-ad-generation`, not a replacement.

- `sop.md` — connect, pull frames, map slots, produce briefs.
- Requires `brand-product-foundation` and a connected Figma account.

Nothing runs on install. Only runs after Figma is connected and the person asks for it.
