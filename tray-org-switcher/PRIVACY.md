# Tray Org Switcher privacy policy

Last updated: 2026-11-10

Tray Org Switcher is a Chrome extension for Tray staff who work in several Tray
organizations. It is published by Tray to the tray.io Google Workspace only.
This policy describes what it handles, where that data lives and who receives it.

## What it handles

- **Tray session tokens.** When you sign in to a Tray org through Okta, the
  extension reads that org's session cookie so it can keep the session and use
  it in the tabs you choose. Tokens are kept only in Chrome's in-memory session
  storage and in the browser's request rules. They are never written to disk by
  the extension, never shown, logged or sent anywhere except to Tray's own API,
  and they are deleted when they expire, when Tray rejects them, when you choose
  Forget, or when Chrome closes.
- **Org details.** For each org: the region, the organization id, the account
  email Tray reports for the session, the name of its Okta tile, and any name
  you give it. These are kept in Chrome's local extension storage so the list
  survives a restart. An org that no longer has a session is removed after 24
  hours unless you star it; Forget removes it at once.
- **Okta tile names and links** on `tray.okta.com`, to name each org and to
  offer "Sign in" for it.
- **Tray and Helix page addresses.** The extension looks at the address of Tray,
  Helix and Okta pages you open, to decide which org a tab should use. It keeps
  an index of Tray object ids (workflows, projects, workspaces) and the org that
  owns each one, so links open in the right org. It does not record other sites
  you visit.
- **Your settings**: default org per region, locks, pinned tabs, favourites.

## Where data goes

Nowhere outside your browser, except Tray's own servers. The extension sends
requests only to Tray API hosts (`api.tray.io` and its regional equivalents),
with the token of the org concerned, to check that a session is still valid, to
read the org's identity and to find which org owns a linked item. It has no
analytics, no tracking, no remote code and no server of its own. Nothing is sold
or shared with anyone, and nothing is used for advertising or credit decisions.

## Your control

Forget removes an org and its token. Removing the extension deletes everything
it stored. An option signs out every org when your screen locks.

## Contact

Tray IT and Security, via the publisher contact on the Chrome Web Store listing.
