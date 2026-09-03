# landing-page-suite: activation

Present while installed. Governs the landing-page workflow in this instance.

## Gate

- Resolve the workspace from Motion context. Read `brand-product-profile.json`. If missing, route
  to `brand-product-foundation`.
- If the official landing-page skills are installed, use them; otherwise follow
  `/agent/brain/landing-page-suite/guide.md`.

## When to run

- Trigger on landing-page asks: summarize/extract a page, CRO-audit or optimize, generate A/B
  tests, or build a page. Pick the matching capability from the guide.

## Flow

1. Always summarize fresh before an audit or experiment backlog.
2. Keep variant/page copy on-brand (brand kit) and claims-safe (profile `claims`).
3. Hand back built pages and reports as openable deliverables.

## Rules

- Fresh summary before optimize/experiments; read prior audit history so shipped fixes aren't
  re-suggested. No budget/targeting/structure recommendations. Voice/claims come from the profile
  and brand kit; never carry another brand's page or voice.
