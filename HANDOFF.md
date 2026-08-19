# LocalWave Signed Releases — Handoff

## Repository role

`livenewme/Localwave-Signed` is the permanent **public distribution repository** for production-signed LocalWave Android APKs.

It is intentionally separate from the private canonical source repository:

`livenewme/LocalWave`

Do not place application source, signing keystores, signing passwords, or recovery credentials here.

## Trusted application identity

Package:

`app.localwave.player`

Trusted release certificate SHA-256:

`34d98c603a2a2c54777c0065ecc3e38c3a4162d4f37d09ae137d004654d39a72`

Key algorithm: RSA 3072-bit

## Current migration state

As of 2026-08-18:

- User has manually installed LocalWave v0.5.0.
- Canonical source is in private `livenewme/LocalWave`.
- Legacy updater/distribution lived under public `livenewme/livenewme/localwave`.
- This repository was created to replace that legacy distribution location.
- The next intended release is **v0.5.1**, a bridge release whose updater discovers future signed releases from this repository.

## Intended updater architecture

Future LocalWave builds should discover releases from this public repository rather than rely on the legacy mutable `latest.json` feed.

Preferred repository layout:

```text
releases/
  v0.5.1/
    LocalWave-v0.5.1.apk
    release.json
  v0.5.2/
    LocalWave-v0.5.2.apk
    release.json
```

The client should enumerate candidate version directories, select a newer valid release, read its metadata, download the APK, and independently verify:

- HTTPS origin
- exact package `app.localwave.player`
- `versionCode` newer than installed
- metadata/version agreement
- SHA-256 of downloaded bytes
- trusted historical LocalWave signer
- signer continuity with installed LocalWave

The updater must reject any candidate failing any of those checks.

## Release requirements

For every new production version:

1. Update canonical private source.
2. Increment `versionCode` and `versionName`.
3. Build release APK.
4. Sign with the established LocalWave signing key.
5. Verify signature, package, version, and certificate.
6. Calculate SHA-256 of exact signed APK.
7. Publish to a new immutable `releases/vX.Y.Z/` directory here.
8. Add matching `release.json`.
9. Verify hosted bytes/hash.
10. Update `CHANGELOG.md` and this handoff.

## Signing key handling

The actual LocalWave release JKS and passwords must remain outside this public repository.

The signing keystore was recovered from historical LocalWave signing backup material during the v0.5.0 migration. Future sessions should use the private canonical repository's documented encrypted recovery workflow when signing access is required.

Never print or commit the keystore password or recovery password here.

## Version immutability

Never replace an APK already published under an existing version directory.

If a release is defective, create a new release with a higher Android `versionCode`.

## Files to keep current

Every production release should update:

- `CHANGELOG.md`
- `HANDOFF.md`
- corresponding `releases/vX.Y.Z/release.json`

`README.md`, `SECURITY.md`, and `RELEASES.md` should only change when repository architecture or policy changes.
