# Landing Page Suite guide

Four chained capabilities. Prefer the official landing-page skills when installed; this guide is
the fallback and the profile-grounding layer.

## Prerequisites

- `brand-product-profile.json` present. Brand kit helpful for voice/claims/visual system.

## 1. Summarize (extract)

- Deep-extract a page into a structured spec: every section, link, image, CTA, component, the
  design system, and the voice. Use a headless browser for JS-rendered/gated pages. Always
  re-fetch fresh; archive prior versions as a changelog.

## 2. Optimize (CRO audit)

- Audit against the ads pointing at the page: message match, awareness-stage alignment, friction,
  proof, CTA architecture. Return the top 3 fixes by expected lift x ease plus a test queue.
  Always run against a fresh summary, never a stale one.

## 3. Experiments (A/B backlog)

- Generate a scored, prioritized backlog of tests grouped by element and hypothesis type, each
  with verbatim current state, variant copy, metric, guardrail, expected lift band, and failure
  mode. Read prior audit history so it never re-suggests shipped fixes. Keep variant copy on-brand
  and claims-safe.

## 4. Build

- Build new pages end to end, grounded in the brand, the audience, and the traffic source. Hand
  back as an openable page. Use the brand kit's visual system and the profile's claims guard.

## Chaining

- Typical flow: summarize -> optimize -> experiments. Build when a new page is needed. Each step
  consumes the previous step's output.

## Guards

- Always summarize fresh before optimize/experiments. Variant and page copy respects the claims
  guard. Do not make budget/targeting/structure recommendations; stay on page and message.
