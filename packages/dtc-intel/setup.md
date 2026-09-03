# DTC Intel setup

## Prerequisites

- `brand-product-profile.json` present. `competitor-roster` recommended (reuse `roster.json`).

## Source selection (ask at setup)

Ask the brand which intel sources to track. Options, pick any:

1. The competitor roster's live ads (via Inspo) as an intel feed.
2. Competitor landing pages and offers (the brand supplies the URLs to watch).
3. Category/DTC reading the brand already trusts (newsletters, docs they paste or save).
4. Ad-hoc notes the team drops in over time.

Only ingest what the brand names. Never scrape sources they didn't approve. For any source that
needs a credential or a blocked host, use the proper connect/secret flow; never ask for a secret
in chat.

## Ingestion + indexing

- Normalize each intel item into a readable markdown record under
  `/agent/brain/<workspace>/data-sources/dtc-intel/<source>/<id>.md` with attribution, date, and
  the source URL.
- Index the records into the brand's searchable corpus (the `corpus-search` tooling) under a
  `dtc-intel` kind so the team can query by meaning.
- Keep raw source text; add a short summary record when it helps retrieval.

## Digest

- Offer a recurring digest (default weekly) of what's new across the tracked sources: notable
  positioning, offers, angles, and page changes, with links. Deliver to the profile's chosen
  destination. Create the routine only after a yes, with clear ownership.

## Guards

- Attribute every intel item to its source with a link and date. Separate observed facts from
  interpretation. Do not present competitor claims as the brand's own or as verified truth.
