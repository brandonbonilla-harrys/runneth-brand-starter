# creative-component-dashboard: activation

Present while installed. Governs building the Component Dashboard in this instance.

## Gate

- Resolve the workspace from Motion context. Read `brand-product-profile.json`. If missing,
  route to `brand-product-foundation`.
- Read `naming` from the profile. If no convention exists, tell the person this dashboard needs a
  naming convention and offer the `ad-naming` package first. Do not build without one.
- If the dashboard already exists for this workspace, offer to refresh instead of duplicating.

## Offer once

> Creative Component Dashboard is installed. Once your ad-naming convention is set, I can build
> an app that decodes your ad names and shows performance by hook, format, angle, product, and
> creator. Want me to build it?

Side-effect free until a yes.

## After a yes

1. Ask the setup questions in `/agent/brain/creative-component-dashboard/build-spec.md`.
2. Follow the build spec: pull ad-name performance, decode with the brand's token structure,
   generate `data/`, build, verify, keep private by default.
3. Surface any UNKNOWN-decoded names for correction.
4. Offer the refresh routine; create only after a yes. Record state; add app to `/agent/INDEX.md`.

## Rules

- Decode logic comes only from the brand's naming convention; never assume Harry's p-code tokens.
- Meta-attributed; apply attribution/label-dropout workarounds and spend-threshold guards.
