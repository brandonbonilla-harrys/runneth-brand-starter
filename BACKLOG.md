# Custom package backlog

Packages still to author into `packages/` and add to `index.json`. Each becomes
workspace-agnostic + self-onboarding using the pattern proven by
`creative-performance-reporting`. Grouped by wave.

## Shipped
- [x] creative-performance-reporting (daily report + monthly strategy digest)

## Wave A — reporting & VoC extensions
- [ ] voc-hook-bank (scored, ready-to-run hooks per product from reviews + ad comments; depends on voc-onboarding)
- [ ] corpus-search (hybrid BM25 + vector retrieval tool over the brand's own indexed corpora)

## Wave B — performance intelligence apps (heaviest)
- [ ] command-center (fatigue scoring, creative DNA, vs-cluster, creator decay, forecast, action layer + pipeline)
- [ ] creative-component-dashboard (decode ad names into components, drill-down performance)
- [ ] producer-cockpit (producer-facing KPIs, hook teardowns, transcripts, competitor inspo)
- [ ] coverage-whitespace-matrix (angle x product tested/untested grid)

## Wave C — competitor & inspo
- [ ] competitor-roster (mapped competitor profiles, weekly auto-refresh)
- [ ] competitor-inspo-board (shareable board of active competitor winners)
- [ ] dtc-intel (weekly cross-cohort pattern tracking)

## Wave D — ad generation
- [ ] static-ad-generation (reference-images-only SOP + claims guard + aspect enforcement + HTML brief)
- [ ] template-library-engine (harvest competitor statics, vision-classify, mint reference-only templates)
- [ ] figma-template-pipeline (competitor-derived editable 4x5 Figma templates + plugin)
- [ ] video-recipe-system (faceless demo/reveal/application video recipes)
- [ ] weekly-creative-batch (scored selection + dedup ledger + learning-log promote/suppress)

## Wave E — ops & foundation
- [ ] meta-budget-pacing (pacing config + weekly pacing/budget-change routines)
- [ ] routine-watchdog (inactive/broken routine alerts + dependency map)
- [ ] brand-kit (identity/voice/visual-system builder skill)
- [ ] landing-page-suite (summary -> optimize -> experiments -> builder skills)

## Generalization checklist per package
- Remove: workspace IDs, ad account IDs, product codes, p-code/growth naming conventions,
  Slack channel IDs, Drive folder IDs, secret names, campaign tokens.
- Replace hardwired product/claims content with a setup step that reads the brand's own
  products, brand context, and claims.
- Add a `package_instruction` activation that offers setup once, resolves the workspace from
  Motion context, discloses side effects, and waits for a yes.
- App packages: ship app source, build the app in the target instance during activation.
