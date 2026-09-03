# Corpus Search setup

Stand up retrieval over the brand's brain corpora.

## Prerequisites

- `brand-product-profile.json` present.
- An OpenAI key connected (`OPENAI_API_KEY`) for embeddings + rerank. Confirm before indexing;
  never ask for a key in chat. Use a stable embedding profile for both indexing and querying.

## What gets indexed (kinds)

- `review` — customer reviews from the connected reviews platform.
- `brief` — the brand's saved creative briefs.
- `dtc-intel` — competitor/DTC intel records (from the `dtc-intel` package).
- `transcript` — video ad transcripts when the brand wants them searchable.
- Add kinds as the brand's corpora grow. Each record keeps source + attribution + date.

## Indexing

- Chunk each corpus, embed with the stable profile, and store vectors + a keyword index under
  `/agent/brain/<workspace>/corpus-search/`. Exclude underscore-prefixed summary docs from the
  searchable set (they're fast-read overviews, not corpus rows).
- Re-index incrementally as new records land; don't re-embed unchanged chunks.

## Querying

- Hybrid keyword + vector query with rerank, filterable by kind, returning ranked chunks with
  source, attribution, and score. Prefer this over grep for meaning-based lookups; keep grep for
  exact-phrase or single-named-file lookups.

## Refresh

- Offer a routine that keeps the indexes current as reviews/briefs/intel accrue; create only after
  a yes.

## Guards

- Retrieval is a ranking aid, not a source of truth for exact counts. Cite the source record +
  attribution on anything surfaced. Keep indexing scoped to this workspace's own corpora.
