# LocalWave Signed Releases

Public distribution repository for production-signed LocalWave Android APKs.

This repository is intentionally **release-only**. The LocalWave application source, build logic, development history, signing keystore, and signing passwords do not live here.

## Purpose

Installed copies of LocalWave use this repository to discover and download newer production APKs.

Every APK published as an active release must:

- use package `app.localwave.player`
- have a monotonically increasing Android `versionCode`
- be signed by the established LocalWave release certificate
- have an exact SHA-256 recorded in `release.json`
- pass package/version/signature verification before publication
- remain immutable once published

## Trusted LocalWave signer

Certificate SHA-256:

`34d98c603a2a2c54777c0065ecc3e38c3a4162d4f37d09ae137d004654d39a72`

Key algorithm: RSA 3072-bit

Keystore and passwords are **not stored here**.

## Repository layout

```text
releases/                 # active in-app update discovery
  v0.5.1/
    LocalWave-v0.5.1.apk
    release.json
  v0.5.2/
    LocalWave-v0.5.2.apk
    release.json

archive/                  # historical only; never searched by updater
  README.md
  v0.5.0/
    release.json
```

## Update discovery beginning with LocalWave v0.5.1

LocalWave queries GitHub's public Contents API for this repository's `releases/` directory, considers version directories, reads each candidate's `release.json`, and chooses the highest valid `versionCode` newer than the installed app.

The updater does **not** enumerate `archive/`.

A candidate APK must then independently pass all of these checks:

1. HTTPS-only transport
2. SHA-256 matches `release.json`
3. package is exactly `app.localwave.player`
4. APK versionCode equals release metadata and is newer than installed
5. APK versionName equals release metadata
6. APK contains the established LocalWave release certificate
7. signer matches the installed LocalWave application

A public repository therefore does not make arbitrary APKs trusted; a production update still requires the private LocalWave signing key.

## Source repository

Canonical LocalWave source remains private:

`livenewme/LocalWave`

## Historical archive

`archive/README.md` contains the durable hash index for recovered historical releases through v0.5.0. Historical binaries can be added there as they are recovered without affecting update discovery.

## Release policy

See [RELEASES.md](RELEASES.md) for the publication contract and [SECURITY.md](SECURITY.md) for trust requirements.

## Current status

- Public signed-artifact repository: active
- Historical archive: initialized
- v0.5.1 canonical source: versionCode 17
- v0.5.1 purpose: migrate in-app update discovery permanently to this repository
- v0.5.1 signed APK: not published until build/sign/verification completes
