# openheader-dist — retired

**This repository is archived and read-only.** It was OpenHeader's self-hosted enterprise
distribution channel: a signed CRX3 plus an `update.xml`, served from the [`dist`](../../tree/dist)
branch.

## Where OpenHeader lives now

- **Source:** [trayio/openheader](https://github.com/trayio/openheader)
- **Distribution:** the Chrome Web Store item `mmlgckcbednmilajhfjaihamacppnalj`, published through
  the store's Verified CRX Uploads by `.github/workflows/cws.yml` in the source repo.
- **Forcelist value** (Google Admin / Jamf `ExtensionInstallForcelist`):
  `mmlgckcbednmilajhfjaihamacppnalj;https://clients2.google.com/service/update2/crx`

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
