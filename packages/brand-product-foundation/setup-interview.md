# Brand & Product setup interview (script)

Run this after the person says yes. Ask **one question at a time**, wait for the answer, and
reflect it back before moving on. Keep it conversational, not a form dump. Save progress to
`state.md` after each phase so an interrupted setup resumes where it left off. Pre-fill anything
you can already see (Motion brand context, connected accounts, existing brain files) and ask the
person to confirm or correct rather than asking cold.

## Phase 0 - Workspace

- Resolve the workspace only from the `Default workspace:` line in the Motion context. If null,
  ask which workspace this setup is for. Everything writes under `/agent/brain/<workspace>/`.

## Phase 1 - Brand basics (one at a time)

1. Brand name and the one-line description of what the brand sells.
2. Category and where they sit in it (challenger, premium, value, etc.).
3. Brand voice in a few words, and any words/tones to avoid.
4. Who the customer is at the highest level (target market).
5. Top 3-5 competitors or the brands they get compared to.

## Phase 2 - Product catalog

1. "How many distinct products should I set up?" Get the list of product names first.
2. Then, for **each** product, one product at a time:
   - Internal/short code (if any) and the on-pack/display name(s).
   - Product category and form factor (what it physically is).
   - Key features or ingredients that matter for creative.
   - Hero benefits (what it does for the customer, in their words).
   - Price and current offer/promo.
   - Where the canonical reference images live (Drive folder, uploads, URL).
   - Primary persona(s) for this product and their top 1-2 objections.
   Reflect the finished product back, then move to the next.

## Phase 3 - Claims & safety (per product or brand-wide)

1. Any claims the brand is allowed to make, and the exact approved framings.
2. Banned words/claims (medical, superlative, comparative, etc.).
3. Required disclaimers and when they must appear.
4. Whether any claims are anchored to a comparison (vs a named competitor or prior product) and
   the disclaimer that must accompany them.

## Phase 4 - Naming convention

1. "Do you already have an ad-naming convention?" If yes, capture the token structure and any
   registries/lookup tables, or where they live.
2. If no, note that the `ad-naming` package can build and persist one, and offer to hand off.

## Phase 5 - Connections (confirm, don't collect secrets)

1. Confirm the Meta ad account is connected for this workspace.
2. Confirm the reviews platform (which one) is connected.
3. Confirm Google Drive access (and the folder(s) that matter).
4. Confirm Slack and which channels reports should go to.
   For anything not connected, point to the right connect flow; never ask for a secret in chat.

## Phase 6 - Measurement

1. Primary KPI for the brand (offer `motion workspace-goal` if set).
2. Attribution stance: Meta-attributed by default unless they run another tool; confirm.
3. Any breakeven ROAS/CPA target to anchor reporting.

## Phase 7 - Delivery preferences

1. Default delivery: a web conversation or specific Slack channels?
2. Preferred timing for daily/weekly/monthly sends.
3. Any format/tone preferences for deliverables (bullets, bolded headers, etc.).

## Close

- Write `brand-product-profile.json` and the per-product `products/<id>.md` files per
  `profile-schema.md`.
- Add all new files to `/agent/INDEX.md`.
- Write `state.md` with `status: complete`.
- Tell the person which downstream packages are now unlocked and configured (reporting, ad-gen,
  dashboards, VoC, competitor, etc. depending on what is installed), and offer to turn on the
  first one.
