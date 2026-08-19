# LocalWave Signed Releases — Handoff

## Repository role

`livenewme/Localwave-Signed` is the permanent **public distribution repository** for production-signed LocalWave Android APKs.

Private canonical source remains:

`livenewme/LocalWave`

Never place application source, signing keystores, signing passwords, or recovery credentials here.

## Trusted application identity

- Package: `app.localwave.player`
- Trusted release certificate SHA-256: `34d98c603a2a2c54777c0065ecc3e38c3a4162d4f37d09ae137d004654d39a72`
- Key algorithm: RSA 3072-bit

## Current migration state — 2026-08-18

- LocalWave v0.5.0 is installed by the user and is the last pre-migration updater generation.
- Canonical v0.5.1 source is now versionCode 17 / versionName 0.5.1.
- v0.5.1 replaces the legacy mutable `latest.json` model with repository-directory discovery from this repo.
- Active discovery is restricted to `releases/`.
- `archive/` has been initialized for historical artifacts and metadata and is intentionally invisible to update discovery.
- v0.5.1 signed APK is not yet published here; do not create final `release.json` until exact signed bytes and SHA-256 are known.

## Active updater architecture beginning with v0.5.1

The app requests:

`https://api.github.com/repos/livenewme/Localwave-Signed/contents/releases?ref=main`

It considers directories matching `v...`, constructs each candidate's raw `release.json` URL, ignores malformed/incomplete directories, and selects the highest `versionCode` newer than the installed build.

Required `release.json` fields:

```json
{
  "versionCode": 17,
  "versionName": "0.5.1",
  "apkUrl": "https://raw.githubusercontent.com/livenewme/Localwave-Signed/main/releases/v0.5.1/LocalWave-v0.5.1.apk",
  "sha256": "<exact signed APK SHA-256>",
  "releaseNotes": "Moves LocalWave update discovery to Localwave-Signed."
}
```

Before installation the client independently verifies:

- HTTPS origin
- release metadata shape
- directory/versionName agreement
- APK URL remains inside that release directory
- exact SHA-256
- package `app.localwave.player`
- APK versionCode and versionName agree with metadata
- versionCode is newer than installed
- historical LocalWave signing certificate
- signer continuity with installed LocalWave

## Archive

`archive/` is historical-only. The updater never enumerates it.

`archive/README.md` contains the durable historical SHA-256 index through v0.5.0. `archive/v0.5.0/release.json` records the verified v0.5.0 identity. Binary historical APKs can be copied into archive version directories when available, but never move an archived version back into active `releases/` unless shipping a genuinely new versionCode.

## Release requirements

For every production version:

1. Update private canonical source.
2. Increment versionCode/versionName.
3. Build release APK.
4. Sign with the established LocalWave key.
5. Verify signature, package, version, and certificate.
6. Calculate SHA-256 of the exact signed APK.
7. Create a new immutable `releases/vX.Y.Z/` directory here.
8. Upload exact signed APK.
9. Verify hosted bytes/hash.
10. Add final `release.json` only after the APK exists and its hash is verified.
11. Update `CHANGELOG.md` and this handoff.

## Signing-key handling

Signing material remains outside this public repo. Use the private canonical repository's documented password-gated recovery flow when signing is required. Never print or commit signing/recovery passwords here.

## Immutability

Never replace a published APK under an existing version directory. A defective release is superseded by a new higher versionCode.
