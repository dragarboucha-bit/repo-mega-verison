# Mega Life Roleplay – public config

This repository holds only the small files the launcher reads. No source code.

| File | Purpose |
|---|---|
| `app.json` | Download links and versions (game files, mods, launcher APK) |
| `servers.json`, `banned.json`, `faq.json`, `changelog.txt` | Launcher content |
| Releases → `MegaLife.apk` | The launcher APK players download when updating |

## Publish a launcher (APK) update

1. Download `MegaLife.apk` from the build in the private code repository (Actions → latest run → Artifacts).
   `UPDATE-INFO.txt` in the same download has the three values for step 3.
2. In this repository: Releases → Draft a new release → pick any new tag (for example `v1.0.25`) →
   attach the file, named exactly `MegaLife.apk` → Publish release.
3. Edit `app.json`: set `apk_version_code`, `apk_version_name` and `apk_sha256` to the values from
   `UPDATE-INFO.txt`. Commit.

Players get the update the next time they open the launcher.
`"apk_mandatory": true` blocks playing until they update; `false` lets them press LATER.

`apk_url` can also be a MediaFire page link (`https://www.mediafire.com/file/...`).

## Publish a DFF/TXD mod update

1. Put the files in one ZIP, using the same folders as the game folder
   (`Android/data/ro.alynsampmobile.launcher/files/`).
2. Upload the ZIP to MediaFire and copy the page link.
3. Edit `app.json`: set `mods_url` to that link and change `mods_version` (1 → 2 → 3 ...). Commit.
