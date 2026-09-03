# Creative Component Dashboard

Breaks the brand's ad names into their components (product, hook, format, angle, creator,
iteration, etc.) and rolls up performance by each component, so the team can see which building
blocks actually drive results and where to double down.

Rebuilt fresh in the brand's instance at setup. It reads the brand's naming convention from the
profile (or from the `ad-naming` package) and pulls that brand's own Meta performance.

- `build-spec.md` — the blueprint: prerequisites, decode logic, data model, layout, refresh.
- Requires `brand-product-foundation` and a naming convention. If the brand has no convention,
  it routes them to the `ad-naming` package first.

Nothing runs on install. Built only after an explicit yes; private by default.
