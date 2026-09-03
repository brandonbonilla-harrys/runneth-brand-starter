# Competitor Roster

Turns the brand's competitors into a tracked roster and keeps a weekly read on what each one is
running, so the team always knows what's live in their category and what shifted.

The roster is **seeded from the competitor names captured in the brand-product profile** and
**enriched with the workspace's followed inspo brands**. At setup it asks the brand which source
to lean on (interview names, followed brands, or both), defaulting to both.

- `setup.md` — how the roster is built, the source-preference question, refresh cadence, output.
- Requires `brand-product-foundation` (reads `brand.competitors`).

Nothing runs on install. The roster and its refresh routine are created only after an explicit
yes. Any app view is private by default.
