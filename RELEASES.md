# LocalWave Release Procedure

This repository is the public distribution endpoint for signed LocalWave Android releases.

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
  "fileName": "LocalWave-v0.5.1.apk",
  "sha256": "<64 lowercase hex characters>",
  "packageName": "app.localwave.player",
  "certificateSha256": "34d98c603a2a2c54777c0065ecc3e38c3a4162d4f37d09ae137d004654d39a72",
  "releaseNotes": "Updater migration to Localwave-Signed."
}
```

## Publication sequence

1. Build the release from the private canonical `livenewme/LocalWave` source repository.
2. Sign the final APK with the established LocalWave release key.
3. Verify package, version, signer, and signature.
4. Calculate SHA-256 from the exact final signed APK.
5. Create `releases/vX.Y.Z/`.
6. Upload `LocalWave-vX.Y.Z.apk`.
7. Re-fetch or otherwise verify the hosted APK bytes and SHA-256.
8. Add `release.json` using the verified final hash.
9. Update this repository's `CHANGELOG.md` and `HANDOFF.md`.
10. Never mutate that version's APK afterward.

## Naming rules

- Directory: `vX.Y.Z`
- APK: `LocalWave-vX.Y.Z.apk`
- Metadata: `release.json`
- Android package: `app.localwave.player`
- `versionCode` must increase monotonically.

## Updater behavior

The client should enumerate candidate release directories, parse release metadata, select the highest newer valid version, then download and verify the corresponding APK.

A malformed directory, bad metadata file, wrong package, stale version, SHA mismatch, or wrong signing certificate must be ignored/rejected.

## Rollback

Do not overwrite an existing release to roll back. Android update continuity depends on monotonically increasing `versionCode` values.

If a prior behavior must be restored, ship a new APK with a higher `versionCode` containing the desired code.
