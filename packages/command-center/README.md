# Creative Command Center

A per-product performance intelligence app. For each of the brand's products it shows what's
scaling, what's fatiguing, how creatives cluster, where each is trending, a short forecast,
benchmark context, and a prioritized action list.

It is **rebuilt fresh in the brand's instance at setup**, not ported. The brand's product list
(from the brand-product profile) defines the tabs and the per-product data files, and every
number comes from that brand's own Motion data.

- `build-spec.md` — the full blueprint: setup questions, Motion data sources, data model, layout,
  build steps, and refresh routine.
- Requires `brand-product-foundation` to have run first (it reads the profile).

Nothing runs on install. The app is built only after an explicit yes, and it defaults to private
(Motion sign-in required) unless the person asks for public.
