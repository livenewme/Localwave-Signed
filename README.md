# LocalWave signed release feed

This branch is the live update feed for LocalWave.

## Current updater release

- Current version: **0.13.36**
- versionCode: **70**
- Package: `app.localwave.player`
- APK: `releases/v0.13.36/LocalWave-v0.13.36-release-signed.apk`
- APK size: **3,069,844 bytes**
- APK SHA-256: `9af17d768a4c5aeae389379cfae11571cb3c996142bcb0f700d10e4d20373510`
- APK Git blob: `7776114ee0e99596a4e7ef8fb4aa5e25df826216`
- Signer certificate SHA-256: `58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba`
- Source branch: `codex/changelog-single-source-v0.13.36`
- Release source head: `52f00111618deb9c2227da9d4c543d3e815a36e8`
- Build: LocalWave **#330** / run `33710209484`

v0.13.36 fixes the in-app Change Log display by retiring the stale duplicate `changelog_recent` resource and using one canonical bundled changelog. CI now checks both the source heading and the changelog actually packaged inside the APK against `versionName`.

v0.13.35 remains the audio-engine feature release underneath this fix: ReplayGain-aware normalization, private on-device loudness analysis, and six-band parametric EQ remain unchanged.

Releases follow APK-first / manifest-last publication. The updater verifies trusted HTTPS hosts, APK SHA-256, package name, version code, and the pinned LocalWave signing certificate before installation.
