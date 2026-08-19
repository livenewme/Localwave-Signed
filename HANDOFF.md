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

## Current migration state — 2026-08-19

- LocalWave v0.5.0 is the last installed generation that reads the legacy distribution endpoint.
- A production v0.5.1 bridge APK has been generated locally from the verified signed v0.5.0 APK.
- Bridge identity: package `app.localwave.player`, versionCode `17`, versionName `0.5.1`.
- Bridge APK SHA-256: `35dd6df688315e76e9940be9e72aa145a434b7f36e35fd04cb289092bd67ffa7`.
- Bridge signer certificate SHA-256: `34d98c603a2a2c54777c0065ecc3e38c3a4162d4f37d09ae137d004654d39a72`.
- The bridge carries a valid APK Signature Scheme v2 signature verified locally against the historical LocalWave certificate.
- The bridge changes the sealed updater manifest endpoint to `https://raw.githubusercontent.com/livenewme/Localwave-Signed/main/current01.json` and bumps only the application version identity; the production v0.5.0 code/resources otherwise remain the bridge baseline.
- `current01.json` is present and records v0.5.1 plus the exact expected APK hash.
- `releases/v0.5.1/release.pending.json` is intentionally inactive until the exact APK is uploaded as `releases/v0.5.1/LocalWave-v0.5.1.apk` and its hosted hash is verified.
- Do **not** create active `release.json` until that binary exists and matches the recorded SHA-256.
- `archive/` remains historical-only and is never part of active update discovery.

## Important v0.5.1 / v0.5.2 distinction

The private canonical `LocalWave` source currently contains the fuller repository-directory discovery updater that enumerates:

`https://api.github.com/repos/livenewme/Localwave-Signed/contents/releases?ref=main`

That source should be treated as the basis for **v0.5.2**, not as a byte-identical reconstruction of the shipping v0.5.1 bridge. v0.5.1 exists only to move already-installed clients away from the legacy repository with the smallest possible production change.

For v0.5.2, keep the canonical directory-discovery implementation and publish a normal source-built release.

## v0.5.1 bridge manifest

`current01.json` contains:

```json
{
  "versionCode": 17,
  "versionName": "0.5.1",
  "apkUrl": "https://raw.githubusercontent.com/livenewme/Localwave-Signed/main/releases/v0.5.1/LocalWave-v0.5.1.apk",
  "sha256": "35dd6df688315e76e9940be9e72aa145a434b7f36e35fd04cb289092bd67ffa7",
  "releaseNotes": "Bridge release: LocalWave now checks the dedicated public Localwave-Signed repository for future signed updates."
}
```

The v0.5.1 updater still independently verifies HTTPS, SHA-256, package identity, version identity, the established release certificate, and signer continuity before installation.

## Active updater architecture beginning with v0.5.2

The canonical updater requests:

`https://api.github.com/repos/livenewme/Localwave-Signed/contents/releases?ref=main`

It considers directories matching `v...`, constructs each candidate's raw `release.json` URL, ignores malformed/incomplete directories, and selects the highest `versionCode` newer than the installed build.

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

`archive/README.md` contains the durable historical SHA-256 index through v0.5.0. Binary historical APKs can be copied into archive version directories when available, but never move an archived version back into active `releases/` unless shipping a genuinely new versionCode.

## Release requirements

For every normal production version after the bridge:

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

Signing material remains outside this public repo. Never print or commit signing/recovery passwords here.

## Immutability

Never replace a published APK under an existing version directory. A defective release is superseded by a new higher versionCode.
