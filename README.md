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

| App | Tag | What it is |
|---|---|---|
| Servatto Kiosk | `kiosk-v*` | Self-order tablet for the counter |
| Servatto Kitchen | `kitchen-v*` | Kitchen display shell |

These are the **sideload** builds — they update themselves and can be set as the tablet's
home screen. The Google Play versions do neither, because Play handles both.

Every build's SHA-256 is published in its release notes and in the manifest the tablets
read. A tablet checks the hash before it installs, so a truncated or tampered download
fails safely rather than badly.

Issues and questions: info@servatto.com
