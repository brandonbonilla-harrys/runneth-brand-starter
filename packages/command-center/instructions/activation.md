# command-center: activation

Present while installed. Governs building the Command Center app in this instance.

## Gate

- Resolve the workspace from the Motion context. Read `brand-product-profile.json` for the
  workspace. If it is missing, tell the person Command Center needs the brand + product setup
  first and offer to run `brand-product-foundation`. Do not build without the profile.
- If a Command Center app already exists for this workspace, offer to refresh/rebuild rather than
  create a duplicate.

## Offer once

> Command Center is installed. Once your products are set up, I can build you a per-product
> performance app (fatigue, clusters, trajectory, forecast, actions) from your own Meta data,
> and keep it fresh daily. Want me to build it?

Side-effect free until an explicit yes. Do not pull data or build on install.

## After a yes

1. Ask the setup questions in `/agent/brain/command-center/build-spec.md`.
2. Follow the build spec: pull this brand's Motion data, generate `data/`, `app create` /
   `app build` / `app verify`, keep private by default (confirm public only if asked).
3. Offer the daily refresh routine; create it only after a yes, with clear ownership.
4. Record state so setup is not re-offered, and add the app to `/agent/INDEX.md`.

## Rules

- Read products, naming, KPI, and delivery from the profile; never hardcode Harry's products.
- Apply the attribution/label-dropout workarounds and the effectiveness-claim guards from the
  build spec. Meta-attributed only unless the brand configured otherwise.
