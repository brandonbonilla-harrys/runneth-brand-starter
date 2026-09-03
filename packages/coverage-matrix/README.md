# Coverage & Whitespace Matrix

A grid of messaging angles down one axis and products (and optionally formats) across the other,
each cell marked tested vs untested, with performance shown where tested. It makes the brand's
creative whitespace obvious: which angle x product combinations have never been tried, and which
tested combinations are working.

Rebuilt fresh in the brand's instance at setup. The products, angles, and personas come from the
brand-product profile; the tested/untested state and performance come from the brand's own
creatives.

- `build-spec.md` — blueprint: setup questions, how coverage is determined, data model, layout,
  refresh.
- Requires `brand-product-foundation`.

Nothing runs on install. Built only after an explicit yes; private by default.
