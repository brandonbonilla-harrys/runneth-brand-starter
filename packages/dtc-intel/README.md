# DTC Intel Corpus

A searchable brain corpus of DTC and competitor intelligence: how competitors position, what
offers and angles they run, landing-page and funnel moves, and category shifts. The team can
query it by meaning ("who's running a bundle discount", "eczema-adjacent angles") and get a
recurring digest of what's new.

Sources are chosen by the brand at setup, so nothing is assumed from any other brand. Pairs with
the `corpus-search` tooling for retrieval; on its own it owns the intel content layer.

- `setup.md` — source selection, ingestion, indexing, and the digest.
- Requires `brand-product-foundation`; works best alongside `competitor-roster`.

Nothing runs on install. Ingestion and any routine start only after an explicit yes.
