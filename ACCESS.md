# For the brand admin — access + install

This is everything the person setting up a new brand instance (Lume, Mando) needs. Two parts:
grant read access to the package repo, then run one install.

## 1. Grant read access to the package repo

The custom packages live in this GitHub repo:

> `brandonbonilla-harrys/runneth-brand-starter`

The new instance's Runneth package backend needs **read** access to it. Ask whoever owns the
Runneth GitHub App / package backend for that instance to add this repo to the App's installation
(read-only is enough). Nothing else in Brandon's GitHub needs to be shared, just this one repo.

You'll know access is working when `package sync` (below) resolves the packages instead of
erroring on the source.

## 2. Install (one time, in the brand's instance)

Run these three lines in the brand's Runneth instance. They only stage files; no setup runs yet.

```
package index-source add runneth-brand-starter brandonbonilla-harrys/runneth-brand-starter@9c311b7a016c32ee150d9baef9e01db0f29cf0da
package intent add-baseline-category brand-starter-26
package sync
```

That installs all 20 packages, frozen to a fixed release so nothing drifts later.

## 3. Then set it up (inside the instance, one yes at a time)

1. **Run Brand & Product Foundation first.** It runs a guided interview and writes the brand's
   product profile that every other package reads. Do this before anything else.
2. **Connect the brand's accounts** as setup asks: Meta, reviews platform, Google Drive, Slack,
   plus OpenAI (search) and the image-generation key (static ads). Secrets go through the secure
   connect flow, never pasted into chat.
3. **Turn on what the brand wants.** Apps rebuild from the brand's own data on a yes; routines are
   created only on a yes, with an owner. Anything they don't want: `package uninstall <package-id>`.

## Notes

- Everything is human-gated: installing stages files, and each package only acts after an explicit
  yes in that instance.
- No Harry's or Flamingo data ships in these packages; each brand configures to its own accounts.
- To ship an update later, we re-freeze to a new commit and the instance re-runs `package sync`.
