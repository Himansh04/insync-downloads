# IN SYNC downloads: notes for Claude

Public host for IN SYNC app update files (APKs) on GitHub Releases. Full picture: README.md and
`insync-knowledge/products/insync-downloads.md`.

This repo is **public**. Everything committed here, and every release, is visible to anyone.

## Commands

```bash
GH_TOKEN=$(gh auth token --user Himansh04) gh release list -R Himansh04/insync-downloads
# Uploading a version: use the exact command printed by insync-site/tools/publish-apk.py
```

## Rules

- IN SYNC work uses the GitHub account **Himansh04** (`GH_TOKEN=$(gh auth token --user Himansh04)`)
  and the Google account **himanshubairagi007@gmail.com**, never the Twopir/work accounts.
- Never commit secrets: keys, keystores, `google-services.json`, service-account JSON and `.env`
  live in `C:\Users\himan\.insync-keys\` or in Firebase/Cloudflare secrets.
- Deploy, publish or release only when Himanshu says so.
- Work on a branch and open a pull request into `main`. Run `/security-review` before merging
  anything that touches payments, sign-in, Firestore rules or secrets.
- Field placeholders are hints ("Your name"), never sample data.
- Public repo: no client names, no internal notes, no keys, no debug details in commits or release
  notes beyond the version, build type and SHA-256.
- Only release builds signed with the app's own release key go out as normal releases; developer
  (debug-key) builds are pre-releases.
- Never replace the file of an existing release: installed apps check the SHA-256.

## Where things are

- Releases: one per app version, tag `<app>-<version>`, APK attached.
- `README.md`: what this repo is.
