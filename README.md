# Alfredo — update channel

Built releases of [Alfredo](https://alfredo.bookoff.me), a native launcher for
macOS. The source code is closed; this repository exists for two things:

- **Releases** — the archives the app downloads when it updates;
- **`appcast.xml`** — the feed it reads to learn a new version exists.

The feed is served at <https://alfredo-updates.bookoff.me/appcast.xml>.

## Why this repository is public

The app downloads updates without authentication, so the files have to be
reachable without it.

This costs nothing in security: every entry in `appcast.xml` carries an EdDSA
signature, and the public key is embedded in the app. Without the private key an
archive cannot be swapped — the app simply refuses to install it. The update
host does not need to be trusted.

## Install

Grab the latest DMG from [Releases](../../releases/latest) and drag Alfredo into
Applications. It updates itself from there.
