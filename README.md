# Runneth Brand Starter

A ready-to-push package bundle for standing up a new brand's Runneth instance (built for
onboarding **Lume** and **Mando**). Hand this whole folder to whoever administers the new
instances. It is designed so each brand can install everything, then deprecate what they
don't want.

## Scope: our packages only

This rollout uses **only the custom packages in this folder**. Motion's off-the-shelf packages
(`ad-naming`, `creative-strategy-foundations`, `creative-strategy-guidance`, `voc-onboarding`,
`meta-onboarding`, `hook-script-mining`, `creator-intel`, `creative-ideation-package`,
`creative-qa`) are intentionally **not** part of this install right now. This bundle is built to
the same package contract they use, so those official packages can be layered on later without
rework if the brands ever want them.

## What's in here

This folder is a **conforming package index** (`index.json`) plus the package sources under
`packages/`. Push it to a git repo the new instances can read, add it as an index source once,
enable the `brand-starter-26` category, and sync. See `INSTALL.md` for the exact steps and
`AUTHORING.md` for the package format.

The 20 custom packages are the systems we built for Harry's & Flamingo, re-authored to be
**workspace-agnostic and self-onboarding**: on first run in a brand's workspace each one
configures itself to that brand's account, products, and connections. The keystone,
`brand-product-foundation`, runs a guided interview and writes a canonical brand-product profile
that every other package reads. Nothing is hardwired to Harry's or Flamingo.

## Structure parity with Motion

Every package here follows the exact structure Motion uses in `Motion-Creative/runneth-apps`:
same index schema, same manifest resource shape, same `agent_brain` / `agent_skills` /
`package_instructions` roots, same `backend-github` source pinning. Runneth OS ingests, stages,
and activates these packages through the same package service it uses for Motion's own. The only
difference is these are served from our repo instead of Motion's.

## What this folder is NOT

- It does not contain Harry's or Flamingo customer data, reviews, or performance numbers.
- It does not install anything by itself. Installing and running setup happens in each brand's
  own instance, human-gated: every package stages files on install and only runs its setup after
  an explicit yes in that instance.
