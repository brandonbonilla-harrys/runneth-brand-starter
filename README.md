# Runneth Brand Starter

A ready-to-push package bundle for standing up a new brand's Runneth instance (built for
onboarding **Lume** and **Mando**). Hand this whole folder to whoever administers the new
instances. It is designed so each brand can install everything, then deprecate what they
don't want.

There are two halves to the handoff, and only one of them needs this folder:

## Half 1 — Off-the-shelf (already published, no folder needed)

Most standard capabilities are already maintained as official Motion packages in
`Motion-Creative/runneth-apps`. A new instance gets them by enabling the right **intent
categories** (or explicit installs). No re-authoring, no copying. See `INSTALL.md` for the
exact manifest. These cover:

| Capability | Official package |
| --- | --- |
| Ad naming SOP + decoder | `ad-naming` |
| Creative analysis / generation / briefing skills | `creative-strategy-foundations` |
| Hook, headline, review-mining standards + strategy engine | `creative-strategy-guidance` |
| VoC ingestion (reviews, ad comments, Reddit, X, Amazon), VoC audit, personas, gap analysis | `voc-onboarding` |
| Meta performance analysis + weekly report design | `meta-onboarding` |
| Hook & script mining (swipe file) | `hook-script-mining` |
| Creator intelligence (roster, leaderboard, recommendations) | `creator-intel` |
| Creative ideation engine (17-Q interview, banks) | `creative-ideation-package` |
| Creative QA | `creative-qa` |

## Half 2 — Custom (this folder)

The systems we built specifically for Harry's & Flamingo that have no official package yet.
This folder is a **conforming package index**: push it to a git repo the new instances can
read, add it as an index source once, and every custom package below becomes installable.
See `INSTALL.md` for the steps and `AUTHORING.md` for the package format.

Custom packages carried here are listed in `index.json`. Each is being authored to be
**workspace-agnostic and self-onboarding**: on first run in a brand's workspace it configures
itself to that brand's account, products, and connections. Nothing is hardwired to Harry's or
Flamingo.

## What this folder is NOT

- It does not contain Harry's or Flamingo customer data, reviews, or performance numbers.
- It does not install anything by itself. Installing and running setup happens in each brand's
  own instance, human-gated, exactly like the official packages.
