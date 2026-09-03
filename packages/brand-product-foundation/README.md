# Brand & Product Foundation

The first thing a new brand instance should set up. It runs a guided interview to learn the
brand and its **actual products**, then writes a canonical **brand-product profile** into the
brain. Every other Runneth package reads that profile, so nothing else has to re-ask who the
brand is, what it sells, what it can and cannot claim, or how it names and reports.

Because a new brand's products are nothing like any other brand's, this package does the heavy
setup up front and asks enough questions to make everything downstream specific to them.

## What it captures

1. **Brand basics** — name, category, positioning, voice, target market, main competitors.
2. **Product catalog** — every product, one at a time: names (internal + on-pack), category,
   form factor, key features/ingredients, hero benefits, price/offer, reference-image location,
   primary personas, top objections.
3. **Claims & safety** — allowed framings, banned language, required disclaimers, per product.
4. **Naming convention** — the brand's own ad-naming taxonomy, or a handoff to the `ad-naming`
   package to build one.
5. **Connections** — confirms Meta ad account, reviews platform, Drive, and Slack.
6. **Measurement** — primary KPI, attribution stance, any breakeven target.
7. **Delivery** — default destinations (web or Slack channels), report timing, tone/format.

## What it writes

- `/agent/brain/<workspace>/brand-product-profile.json` — the canonical machine-readable profile.
- `/agent/brain/<workspace>/products/<product-id>.md` — one readable spec per product.
- A `brand-product-foundation/state.md` marker so setup resumes instead of restarting.

See `setup-interview.md` for the full question script and `profile-schema.md` for the exact
profile shape downstream packages consume.

## What it does NOT do

- It does not carry any other brand's products, claims, reviews, or numbers.
- It does not run on install. Setup starts only after an explicit yes, one question at a time.
