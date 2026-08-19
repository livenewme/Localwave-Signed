# LocalWave Signed Releases

Public distribution repository for production-signed LocalWave Android APKs.

This repository is intentionally **release-only**. The LocalWave application source, build logic, development history, and signing credentials do not live here.

## Purpose

Installed copies of LocalWave use this public repository as a trusted distribution location for newer production APKs.

Every APK published here must:

- use package name `app.localwave.player`
- have a monotonically increasing Android `versionCode`
- be signed by the established LocalWave release certificate
- pass package/version/signature verification before publication
- be immutable once published

## Trusted LocalWave signer

Certificate SHA-256:

`34d98c603a2a2c54777c0065ecc3e38c3a4162d4f37d09ae137d004654d39a72`

Key algorithm: RSA 3072-bit

Keystore and passwords are **not stored in this repository**.

## Repository layout

```text
releases/
  v0.5.1/
    LocalWave-v0.5.1.apk
    release.json
  v0.5.2/
    LocalWave-v0.5.2.apk
    release.json
```

Each version directory is immutable after publication.

## Update discovery

LocalWave will discover newer versions from this repository, then independently verify the APK before installation.

The updater must never trust a filename alone. A candidate update must pass all of the following checks:

1. HTTPS-only download
2. package name is exactly `app.localwave.player`
3. APK `versionCode` is newer than the installed build
4. APK version agrees with release metadata
5. SHA-256 matches the published release record
6. APK is signed by the established LocalWave release certificate
7. signer matches the currently installed LocalWave application

If any check fails, the update must be rejected.

## Source repository

The canonical LocalWave source repository is private:

`livenewme/LocalWave`

This public repository exists only to distribute signed production artifacts.

## Release policy

See [RELEASES.md](RELEASES.md) for the publication procedure and [SECURITY.md](SECURITY.md) for signing and trust requirements.

## Current status

Repository initialized for the post-v0.5.0 updater migration.

The first release intended to use this repository as its permanent update source is the v0.5.1 bridge release.
