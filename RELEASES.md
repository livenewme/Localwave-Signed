# LocalWave Release Procedure

This repository is the public distribution endpoint for signed LocalWave Android releases.

## Active vs archived releases

The LocalWave updater enumerates **only**:

```text
releases/
```

Historical builds belong under:

```text
archive/
```

Anything under `archive/` is invisible to normal in-app update discovery.

## Version layout

Each production version gets its own immutable directory:

```text
releases/vX.Y.Z/
```

Required files:

```text
LocalWave-vX.Y.Z.apk
release.json
```

## `release.json` contract

Example:

```json
{
  "versionCode": 17,
  "versionName": "0.5.1",
  "apkUrl": "https://raw.githubusercontent.com/livenewme/Localwave-Signed/main/releases/v0.5.1/LocalWave-v0.5.1.apk",
  "sha256": "<64 lowercase hex characters>",
  "releaseNotes": "Moves LocalWave update discovery to Localwave-Signed."
}
```

The current app consumes `versionCode`, `versionName`, `apkUrl`, `sha256`, and optional `releaseNotes`. The APK itself remains the final authority for package/version/signing identity.

## Publication sequence

1. Build the release from private canonical `livenewme/LocalWave`.
2. Sign the final APK with the established LocalWave release key.
3. Verify package, version, signer, and APK signature.
4. Calculate SHA-256 from the exact signed APK.
5. Create `releases/vX.Y.Z/`.
6. Upload `LocalWave-vX.Y.Z.apk`.
7. Verify the hosted APK bytes and SHA-256.
8. Add `release.json` with the exact hosted APK URL and verified hash.
9. Update `CHANGELOG.md` and `HANDOFF.md`.
10. Never mutate that version's APK afterward.

## Naming rules

- Directory: `vX.Y.Z`
- APK: `LocalWave-vX.Y.Z.apk`
- Metadata: `release.json`
- Android package: `app.localwave.player`
- `versionCode` must increase monotonically.

## Updater behavior beginning with v0.5.1

The app requests GitHub's public Contents API for:

```text
/repos/livenewme/Localwave-Signed/contents/releases?ref=main
```

It considers only directories matching `v...`, reads each directory's `release.json`, ignores malformed or incomplete entries, and selects the candidate with the highest `versionCode` above the installed build.

Before installation, the downloaded APK must still pass:

- exact SHA-256 from `release.json`
- package `app.localwave.player`
- exact metadata `versionCode` and `versionName`
- higher versionCode than installed
- established LocalWave certificate SHA-256
- signer continuity with the installed LocalWave app

## Rollback

Never overwrite an existing production release. To restore older behavior, publish new code with a higher Android `versionCode`.
