# OpenHeader Privacy Policy

_Last updated: 1 September 2026_

OpenHeader ("the extension") has **no server, no analytics, and no tracking**, and never transmits
your data to the developer or to any third party. The extension does have one feature that copies
data off your device — profile sync, described below — and that copy goes to **your own browser
account**, not to us.

## What the extension stores

- The header rules, profiles, colors, and settings you configure are stored **on your device** using
  the browser's `storage.local` API. This may include header names and values you type in (which
  could include tokens, cookies, or other secrets), and they are stored unencrypted.
- **Profile sync (on by default).** OpenHeader can also copy your profiles into your browser
  account's sync storage (`storage.sync`), so they follow you to your other signed-in devices. This
  is **enabled by default**, including when an existing installation updates to a version that
  supports it.
  - **Your header values are part of that copy.** If a profile contains an `Authorization` token or a
    `Cookie` value, it is stored in your browser account too, and we do not encrypt it.
  - That copy is held by your browser vendor — Google for Chrome and Chromium browsers, Mozilla for
    the Firefox build — under **your own account**, and is protected by that account's own controls.
    A Chrome sync passphrase, for example, makes your synced data end-to-end encrypted.
  - It is **never sent to the developer of OpenHeader or to any third party.** We operate no server
    and never receive it.
  - Only your profiles and your light/dark theme preference are synced. Whether the extension is
    paused, and which profile is active, deliberately stay local to each device.
  - You can turn sync off at any time in the extension's options page. Once it is off, a **Remove
    synced copy** button appears, which deletes the copy already stored in your browser account. Your
    profiles on the device are kept either way, and turning sync off is never undone by a later
    update.
- The Import/Export feature reads and writes a JSON file **locally, at your request**. The developer
  does not receive it. Exported files are unencrypted, so store and share them with care.

## What the extension does on the pages you visit

- **A warning banner for impersonation headers.** OpenHeader runs a small script on the pages you
  visit so it can warn you when a rule that impersonates another user — currently a rule setting the
  `x-tray-admin-impersonate` header — is switched on and applies to the page you are looking at. It
  draws a bar at the top of that page saying so, and does nothing else.
- **What that script reads:** your own stored profiles, and the **address of the page** — the URL
  only, so it can work out whether your own URL filters cover it. It does **not** read the page's
  content, its text, its forms, or anything you type into it.
- **What it sends:** nothing leaves your device — there is no server for it to reach. Inside the
  extension it exchanges exactly one thing with its own background script: whether you have collapsed
  the bar in this tab. The page's address is examined on your device and is never stored, logged, or
  transmitted anywhere.
- **What it remembers:** if you collapse the bar, that single fact is remembered for that browser tab
  only, in `storage.session`, which the browser clears when you close it. It is not synced.

## What the extension does NOT do

- Does not transmit any data to the developer or to third parties. The only data that leaves your
  device is the profile sync described above, which goes to your own browser account.
- Does not collect personally identifiable information, financial data, location, communications,
  browsing history, or user activity.
- Does not use analytics, telemetry, tracking, or remote/hosted code.
- Does not read the content or bodies of your web requests or responses. Headers are changed through
  the browser's `declarativeNetRequest` API, which applies rules you define without ever exposing
  request or response contents to the extension.
- Does not read the content of the pages you visit. The warning banner described above sees a page's
  address and nothing more, and only to decide whether to warn you.

## Permissions

- **`declarativeNetRequestWithHostAccess`** and host access are used to apply your header rules to
  the requests and sites you choose, and to show the impersonation warning banner on the pages those
  rules cover. The extension asks for broad host access because your rules can target any site; it
  adds no permission beyond what modifying headers already required.
- **`storage`** is used to persist your configuration on this device, and — while sync is enabled —
  to replicate your profiles to your own browser account.
- **`alarms`** is used solely to schedule the extension's internal sync timers: batching a burst of
  edits into a single sync write, and periodically checking for changes made on your other devices.
  It performs no network requests and reads nothing beyond your own profiles.

## Data retention and deletion

- Your configuration stays in local browser storage until you remove it (delete rules/profiles) or
  uninstall the extension, which clears its storage.
- If sync has been enabled, a copy also stays in your browser account until you remove it. Turn sync
  off in the options page and use **Remove synced copy**, or clear it through your browser account's
  own sync controls. Uninstalling the extension does **not** by itself remove the synced copy.

## Contact

Questions or concerns about this policy: email <privacy@tray.io>.

## Changes

Any updates to this policy will be published at its public URL.
