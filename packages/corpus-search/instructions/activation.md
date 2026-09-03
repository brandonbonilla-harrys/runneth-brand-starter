# corpus-search: activation

Present while installed. Governs corpus retrieval setup in this instance.

## Gate

- Resolve the workspace from Motion context. Read `brand-product-profile.json`. If missing, route
  to `brand-product-foundation`.
- Confirm an OpenAI key is connected for embeddings/rerank. If not, offer the connect/secret flow;
  never ask for a key in chat.

## Offer once

> Corpus Search is installed. I can index your reviews, briefs, transcripts, and intel so you can
> search them by meaning in about a second. Want me to set it up?

Side-effect free until a yes. Do not index on install.

## After a yes

1. Follow `/agent/brain/corpus-search/setup.md`: confirm kinds, index, verify a query returns
   ranked chunks with attribution.
2. Offer a keep-current routine; create only after a yes.
3. Index the corpus location in `/agent/INDEX.md`.

## Rules

- Retrieval is a ranking aid, not exact counts; cite source + attribution. Same embedding profile
  for indexing and querying. Scope to this workspace's own corpora only.
