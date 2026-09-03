# Install manifest

Run these steps once per brand instance (Lume, Mando). Everything is human-gated: `install`
and `sync` only stage files; each package's setup runs later after an explicit yes in that
instance.

## Step 1 — Off-the-shelf packages (from Motion-Creative/runneth-apps)

Enable the intent categories the new instance should carry. These pull the official packages
directly; the new instance already reaches the same source this bundle came from.

```
package intent add-baseline-category baseline
package intent add-baseline-category ad-naming-26
package intent add-baseline-category ai-training-club-26
package intent add-baseline-category creative-qa-26
package sync
```

Then the two onboarding packages, which are explicit installs (installPolicy: manual):

```
package install meta-onboarding
package install voc-onboarding
```

Creative ideation ships from a dedicated branch ref rather than the main index:

```
package install Motion-Creative/runneth-apps/creative-ideation-package@codex/jose-creative-ideation-v1
```

> Note: confirm exact refs with whoever owns `runneth-apps`. `baseline` is usually already on
> by default; adding it is harmless.

## Step 2 — Custom packages (this bundle)

This bundle is pushed to `github.com/brandonbonilla-harrys/runneth-brand-starter@main`. Register
it as an index source on each instance, then sync:

```
package index-source add runneth-brand-starter brandonbonilla-harrys/runneth-brand-starter@main
package sync
```

(Use whatever git-ref form the target instance's package system expects for a GitHub source; the
index.json sources are set to owner `brandonbonilla-harrys`, repo `runneth-brand-starter`, ref
`main`.)

Or, simplest for a one-time drop, clone this folder into the instance and install locally:

```
package install ./runneth-brand-starter/packages/<package-id>
```

The custom packages available in this bundle are listed in `index.json`. Category
`brand-starter-26` auto-installs the set once the index source is registered:

```
package intent add-baseline-category brand-starter-26
package sync
```

## Step 3 — Prune

Anything a brand doesn't want:

```
package uninstall <package-id>
```

That removes the package's staged files and blocks managed sync from re-adding it. Reversible
with `package restore <package-id>`.
