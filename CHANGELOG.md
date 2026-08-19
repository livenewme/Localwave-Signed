# Changelog

All production distribution changes to `livenewme/Localwave-Signed` are recorded here.

## 2026-08-18

### v0.5.1 migration preparation

- Added `archive/` as a historical-only namespace that the app never enumerates for updates.
- Added a durable SHA-256 index for recovered historical releases through v0.5.0.
- Added `archive/v0.5.0/release.json` with the verified v0.5.0 identity.
- Finalized the active `releases/vX.Y.Z/` contract used by LocalWave v0.5.1 and later.
- Updated the release metadata contract to include the exact hosted `apkUrl` and signed-APK SHA-256.
- Canonical LocalWave v0.5.1 source now uses versionCode 17 and discovers future updates from this repository instead of the legacy `latest.json` feed.

### Repository initialization

- Established this repository as the public signed-APK distribution home for LocalWave.
- Added release-only repository policy.
- Added trusted signer fingerprint documentation.
- Added immutable version-directory convention under `releases/`.
- Added release metadata contract via `release.json`.
- Added release security and publication procedures.
- Reserved v0.5.1 as the bridge release that migrates LocalWave away from the legacy update feed.
