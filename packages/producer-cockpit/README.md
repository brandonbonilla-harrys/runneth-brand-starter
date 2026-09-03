# Producer Cockpit

A video-producer-facing app. It surfaces the brand's top video ads with hook and script
teardowns (using the actual transcripts), recent work, and a feed of live competitor and inspo
video examples worth borrowing from.

Rebuilt fresh in the brand's instance at setup, populated from that brand's own Meta creatives
(transcripts + summaries) and competitor/inspo pulls.

- `build-spec.md` — blueprint: setup questions, data sources (transcripts, competitor/inspo),
  data model, layout, refresh.
- Requires `brand-product-foundation`.

Nothing runs on install. Built only after an explicit yes; private by default.
