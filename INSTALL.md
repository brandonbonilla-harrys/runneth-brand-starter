# Install manifest (ours only)

Run these steps once per brand instance (Lume, Mando). This install uses **only the custom
packages in this bundle**. Motion's off-the-shelf packages are intentionally not part of it.

Everything is human-gated: `index-source add`, `install`, and `sync` only stage files. Each
package's setup runs later, after an explicit yes in that instance.

## Step 1 — Register this bundle and turn it on

This bundle is pushed to `github.com/brandonbonilla-harrys/runneth-brand-starter`. Its packages
are **pinned to a frozen commit** so what a brand installs cannot drift when we edit the repo
later (see "Frozen snapshot" below). Register it as an index source, enable the category, sync:

```
package index-source add runneth-brand-starter brandonbonilla-harrys/runneth-brand-starter@9c311b7a016c32ee150d9baef9e01db0f29cf0da
package intent add-baseline-category brand-starter-26
package sync
```

That commit is the frozen release. Its `index.json` pins every package's contents to commit
`aa8d1d9`, so the brand installs an immutable snapshot. (`@main` also works and always points at
the latest frozen pin; use the SHA when you want the install locked to exactly this release.)

That stages all 20 custom packages. (Use whatever git-ref form the target instance's package
system expects for a GitHub source; every package's contents resolve at the frozen commit
recorded in `index.json`.)

Simplest one-time alternative, clone this folder into the instance and install locally:

```
package install ./runneth-brand-starter/packages/<package-id>
```

## Step 2 — Set up, starting with the keystone

Setup happens inside each brand's instance, one yes at a time:

1. **Run Brand & Product Foundation first.** It offers a guided interview (brand, every product,
   claims, naming, connections, KPI, delivery) and writes `brand-product-profile.json`, which
   every other package reads. Nothing else should be set up before this.
2. **Connect accounts** as setup asks: Meta, the reviews platform, Google Drive, Slack, plus
   OpenAI (corpus search) and the image-generation key (static generation). Secrets go through
   the connect/secret flows, never pasted into chat.
3. **Turn on what the brand wants.** App packages rebuild a fresh app from the brand's own data on
   a yes; routine packages create their routine only on a yes, with an owner.

## Step 3 — Prune

Anything a brand doesn't want:

```
package uninstall <package-id>
```

Removes the package's staged files and blocks managed sync from re-adding it. Reversible with
`package restore <package-id>`.

## Frozen snapshot

Every package entry in `index.json` pins `source.ref` to a fixed commit SHA, mirroring how
Motion pins its own packages. This means a brand's install is frozen: later edits or additions on
our `main` branch do not change what an already-installed brand is running until we deliberately
re-pin and they re-sync. To ship an update, bump the pin to a new commit and have the instance
`package sync`.
