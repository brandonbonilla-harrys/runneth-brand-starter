# Competitor Roster setup

## Prerequisites

- `brand-product-profile.json` present (reads `brand.competitors`).

## Source-preference question (ask at setup)

Ask the brand which source to build the roster from:

1. The competitor names from the foundation interview,
2. The workspace's followed inspo brands, or
3. Both (default).

Default to both: seed from the interview names, then enrich with followed brands. Respect their
choice if they pick one source.

## Building the roster

- Resolve each named competitor with `motion inspo brands --search-term "<name>"`. Brand search
  is fuzzy, so confirm identity (domain, page) before locking a brand id; never assume the top
  hit is right.
- For followed brands, use `motion inspo brands` with no search term (or the followed sort).
- Save the resolved roster to `/agent/brain/<workspace>/competitor-roster/roster.json`: per
  competitor, the confirmed brand id, name, domain, and why it's on the roster (named / followed).
- Surface any competitor name that could not be resolved and ask for the right handle or URL.

## Weekly read

- For each roster brand, pull what's live: `motion inspo unique-creatives --brand-id <id>
  --brand-names-by-id '{...}'`, optionally sorted by `impressionRank` for a single brand.
- Summarize per brand: how many live ads, notable new formats/angles, what's worth borrowing,
  what shifted since last week. Keep competitor items attributed with links.

## Output + refresh

- Deliver the weekly read to the brand's chosen destination (from the profile's delivery prefs).
- Offer a weekly refresh routine; create only after a yes, with clear ownership. The routine
  re-pulls each roster brand and posts the summary.

## Guards

- `impressionRank` is Motion's best competitor signal, not true performance; say so. Single-brand
  only for `impressionRank`. Keep brand attribution and links on every competitor creative shown.
