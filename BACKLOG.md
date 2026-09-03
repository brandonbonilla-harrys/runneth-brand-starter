# Custom package backlog

Packages still to author into `packages/` and add to `index.json`. Each becomes
workspace-agnostic + self-onboarding using the pattern proven by
`creative-performance-reporting`. Grouped by wave.

## Shipped
- [x] brand-product-foundation (KEYSTONE: deep guided product setup interview + canonical brand-product profile that every other package reads)
- [x] creative-performance-reporting (daily report + monthly strategy digest)

> Deep-pass decision: brands' products differ completely, so every downstream package reads the
> brand-product profile and, where relevant, adds its own setup questions. No product logic is
> hardcoded; each package configures per brand at setup.

## Wave A — reporting & VoC extensions
- [ ] voc-hook-bank (scored, ready-to-run hooks per product from reviews + ad comments; depends on voc-onboarding)
- [ ] corpus-search (hybrid BM25 + vector retrieval tool over the brand's own indexed corpora)

## Wave B — performance intelligence apps (rebuild-on-setup) [SHIPPED]
- [x] command-center (fatigue, clusters/DNA, trajectory, forecast, benchmark, action layer)
- [x] creative-component-dashboard (decode ad names into components, drill-down performance)
- [x] producer-cockpit (top-ad hook/script teardowns with transcripts, recent work, competitor inspo)
- [x] coverage-matrix (angle x product tested/whitespace grid)

> All Wave B packages are rebuild-on-setup: activation scaffolds a fresh app in the target
> instance from that brand's own Motion data, driven by the brand-product profile. No Harry's app
> source is ported.

## Wave C — competitor & inspo [SHIPPED]
- [x] competitor-roster (mapped competitor profiles, weekly read; seeds from profile competitors + followed brands, brand chooses at setup)
- [x] competitor-inspo-board (rebuild-on-setup browsable competitor/inspo board, video-only aware)
- [x] dtc-intel (searchable DTC/competitor intel corpus + digest, brand-chosen sources)

## Wave D — ad generation [SHIPPED]
- [x] static-ad-generation (Gemini reference-image flow, claims guard, 4x5 enforcement, HTML brief; product specifics from profile)
- [x] template-library-engine (harvest competitor statics, vision-classify, dedupe, mint reference-only templates)
- [x] figma-template-pipeline (optional: pull Figma frames, map slots, generation-ready briefs)
- [x] video-recipe-system (recipes from real transcripts: hook + structure + shot list)
- [x] weekly-creative-batch (scored selection + generation + approval cards; agent-mode routine on consent)

> Ad-gen packages pinned to the Gemini reference-image flow. All product fidelity, claims, and
> naming come from the brand-product profile; no Harry's products, GADV scheme, or p-code naming.

## Wave E — ops, VoC & foundation [SHIPPED]
- [x] voc-hook-bank (ad-ready hooks from reviews + comments, verbatim quote + attribution)
- [x] corpus-search (hybrid keyword + vector retrieval over the brand's corpora)
- [x] meta-budget-pacing (daily pacing vs plan, anomaly flags, attribution/label workarounds; reporting only)
- [x] routine-watchdog (read-only routine health check; owner-gated, never edits routines it doesn't own)
- [x] brand-kit (identity/voice/visual-system builder from profile + live site)
- [x] landing-page-suite (summarize -> optimize -> experiments -> build)

> ALL WAVES SHIPPED. 20 custom packages live in index.json with source owner/repo/ref filled
> (brandonbonilla-harrys/runneth-brand-starter@main).

## Generalization checklist per package
- Remove: workspace IDs, ad account IDs, product codes, p-code/growth naming conventions,
  Slack channel IDs, Drive folder IDs, secret names, campaign tokens.
- Replace hardwired product/claims content with a setup step that reads the brand's own
  products, brand context, and claims.
- Add a `package_instruction` activation that offers setup once, resolves the workspace from
  Motion context, discloses side effects, and waits for a yes.
- App packages: ship app source, build the app in the target instance during activation.
