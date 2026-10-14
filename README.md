# IN SYNC downloads

Public download host for IN SYNC app update files (APKs), served to installed IN SYNC apps over
https from GitHub Releases.

**Status:** live · **Platforms:** GitHub Releases (files for Android apps) · **Owner:** Himanshu

## What it does

- Holds one GitHub Release per app version, tagged `<app>-<version>`, with the APK attached.
- Installed IN SYNC apps download the update from the release link and check its SHA-256 before
  installing; a changed or broken download is refused.
- Developer builds (debug key) are marked as pre-releases and say so in their title.

## Who it is for

The installed IN SYNC apps that update themselves, and the IN SYNC founders who publish versions.

## Tech

No code. Files only, on GitHub Releases. The version details each app reads (link, SHA-256, size,
notes) are published from the IN SYNC studio desk, not from this repo.

## Run it locally

Nothing to run.

## Build and release

Each app's release APK is built in its own repo. `tools/publish-apk.py <app-id> <release.apk>` in
the `insync-site` repo checks the build and prints the version, size, SHA-256 and the
`gh release create` command that uploads it here. Check the live download (same size and SHA-256)
before publishing the version in the desk. Every release of an app must be signed with that app's
release key, or it will not install over the previous one. Publish only when Himanshu says so.

## Where things live

| What | Where |
|---|---|
| Secrets / keystore | `C:\Users\himan\.insync-keys\` (never in git; this repo is public) |
| Backend | none (GitHub Releases) |
| App id / package | one release tag per app version, `<app>-<version>` |
| Live URL | https://github.com/Himansh04/insync-downloads/releases |

## More

- Docs: [docs/README.md](docs/README.md)
- Knowledge base page: `insync-knowledge/products/insync-downloads.md`
- Repo standard: `insync-knowledge/engineering/repo-standard.md`

## From the earlier README (kept word for word)

> insync-downloads

IN SYNC app update files (APKs) served to installed apps over https. Each release = one app version; installed apps check the SHA-256 before installing.
