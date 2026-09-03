# Corpus Search

Gives the brand fast retrieval over its indexed corpora (customer reviews, briefs, transcripts,
DTC intel) by meaning, not just keywords. Hybrid keyword + vector search that returns ranked
chunks in about a second, so the team can ask "who mentions dryness after week two" and get real
quotes instead of grepping files.

Reads the brand-product profile. Uses the brand's OpenAI key for embeddings + rerank. Underpins
`voc-hook-bank`, `dtc-intel`, and review/brief lookups.

- `setup.md` — what gets indexed, the index kinds, and how querying works.
- Requires `brand-product-foundation` and an OpenAI key connection.

Nothing runs on install. Indexing happens only after an explicit yes.
