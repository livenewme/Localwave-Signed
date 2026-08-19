# Changelog

All production distribution changes to `livenewme/Localwave-Signed` are recorded here.

## 2026-08-19

### v0.5.1 bridge finalized

- Generated the production v0.5.1 bridge APK from the verified signed v0.5.0 production APK.
- Bumped application identity to versionCode 17 / versionName 0.5.1.
- Replaced the legacy sealed update endpoint with `https://raw.githubusercontent.com/livenewme/Localwave-Signed/main/current01.json`.
- Signed v0.5.1 with the established LocalWave RSA release key using APK Signature Scheme v2.
- Independently verified the v2 signature and historical certificate fingerprint.
- Final APK SHA-256: `35dd6df688315e76e9940be9e72aa145a434b7f36e35fd04cb289092bd67ffa7`.
- Added `current01.json` for the bridge-generation updater.
- Added inactive `releases/v0.5.1/release.pending.json`; it must become `release.json` only after the exact APK is uploaded and the hosted SHA-256 is verified.
- Advanced private canonical source to v0.5.2 / versionCode 18 so the fuller repository-directory discovery implementation has a distinct release identity.

## 2026-08-18

### v0.5.1 migration preparation

- Added `archive/` as a historical-only namespace that the app never enumerates for updates.
- Added a durable SHA-256 index for recovered historical releases through v0.5.0.
- Added `archive/v0.5.0/release.json` with the verified v0.5.0 identity.
- Finalized the active `releases/vX.Y.Z/` contract.
- Added the release metadata contract with exact hosted `apkUrl` and signed-APK SHA-256.

### Repository initialization

- Established this repository as the public signed-APK distribution home for LocalWave.
- Added release-only repository policy.
- Added trusted signer fingerprint documentation.
- Added immutable version-directory convention under `releases/`.
- Added release security and publication procedures.
- Reserved v0.5.1 as the bridge release that migrates LocalWave away from the legacy update feed.
