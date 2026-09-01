# openheader-dist — retired

**This repository no longer distributes anything.** It was OpenHeader's self-hosted enterprise
distribution channel: a signed CRX3 plus an `update.xml`, served from the [`dist`](../../tree/dist)
branch.

It is kept public, and **not archived**, for one live purpose: it hosts OpenHeader's published
[privacy policy](PRIVACY.md) — see below. Do not archive or delete this repository without moving
that first.

## Where OpenHeader lives now

- **Source:** [trayio/openheader](https://github.com/trayio/openheader)
- **Distribution:** the Chrome Web Store item `mmlgckcbednmilajhfjaihamacppnalj`, published through
  the store's Verified CRX Uploads by `.github/workflows/cws.yml` in the source repo.
- **Forcelist value** (Google Admin / Jamf `ExtensionInstallForcelist`):
  `mmlgckcbednmilajhfjaihamacppnalj;https://clients2.google.com/service/update2/crx`

## What this repository still serves

[`PRIVACY.md`](PRIVACY.md) is OpenHeader's published privacy policy. The Chrome Web Store listing
points at its raw URL, so it must stay publicly readable by anyone, signed in or not:

    https://raw.githubusercontent.com/trayio/openheader-dist/main/PRIVACY.md

It lives here because the policy has to be reachable anonymously by a store reviewer, and
`trayio/openheader` is private — the org disables public GitHub Pages
(`members_can_create_public_pages: false`), so it cannot publish one itself.

**This copy is a mirror. Do not edit it here.** The source of truth is `PRIVACY.md` in
[trayio/openheader](https://github.com/trayio/openheader), where it sits next to the code it
describes and is reviewed in the same pull request as any change to what the extension stores,
sends, or reads. That repo's CI fetches the URL above on every run and fails if the two have
drifted, so an edit made here alone will break its build rather than quietly diverge.

## Why it was retired

Chrome requires a Web Store **publisher proof** on force-installed extensions. A self-hosted CRX
only carries our developer proof, so Chrome rejected updates from this channel with
`CRX_REQUIRED_PROOF_MISSING` — which silently froze the fleet on an old version. Only the Web Store
can add that proof.

Verified CRX Uploads does not preserve a self-hosted key's id — the store re-packages each upload
with the item's own key — so the published extension id changed from
`bmelmpkhocjoenaejlpfchgedojiadgp` (this channel) to `mmlgckcbednmilajhfjaihamacppnalj` (the store
item). The fleet was re-forcelisted onto the new id and the old entry removed.

The `dist` branch is left as it was, for history: it still holds `openheader-0.1.{1,2,3}.crx` and the
final `update.xml` (last publish 0.1.3, 2026-07-10). Nothing consumes it.
