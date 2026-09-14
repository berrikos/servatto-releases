# Servatto releases

Installers for the Servatto tablet apps. **No source code lives here** — this repository
exists only because a shop tablet has to be able to download an APK without signing in to
anything, and release assets on a private repository cannot.

## Don't download from this page

Use **https://app.servatto.com/download**.

That page always points at the current build, which means a printed setup sheet, a QR code
stuck to a box, or a link in an old email keeps working after every release. The permanent
address of the newest Kiosk build is:

    https://app.servatto.com/download/servatto-kiosk.apk

## What is here

| App | Where | What it is |
|---|---|---|
| Servatto Kiosk | release `kiosk-v*` | Self-order tablet for the counter |
| Servatto Kitchen | release `kitchen-v*` | Kitchen display shell |
| Servatto Screen | `apk/` in this tree | Customer display for a television |

## Why Screen is in the tree and not on a release

Kiosk and Kitchen are release assets, which is the right shape: a tag per build,
notes alongside it, and nothing heavy in the git history. Screen 1.0.0 is committed
into `apk/` instead, because the build was produced somewhere that could push to this
repository but could not create a release.

It works — a public raw URL needs no sign-in, which is the only thing a shop tablet
actually requires — but it is the exception, not the pattern. **Move it to a
`screen-v1.0.0` release when convenient**, then update `downloadUrl` in
`web/downloads/screen-builds.json` over in the app repository and delete `apk/`.
Nothing breaks in between: the manifest is the only thing that points at these bytes,
and it can point at either.

These are the **sideload** builds — they update themselves and can be set as the tablet's
home screen. The Google Play versions do neither, because Play handles both.

Every build's SHA-256 is published in its release notes and in the manifest the tablets
read. A tablet checks the hash before it installs, so a truncated or tampered download
fails safely rather than badly.

Issues and questions: info@servatto.com
