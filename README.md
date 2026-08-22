# LocalWave signed release feed

This branch is the live update feed for LocalWave.

- Current version: 0.13.7
- versionCode: 41
- Package: app.localwave.player
- APK SHA-256: f8ba902e1a282aa32eb80b70d680942c8c2b3b32dd7411ba032ef864b5726fc1
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba

v0.13.7 adds persistent manual Whole House calibration with baseline-relative receiver timing and 50 ms / 5 ms Advance/Delay trims.

Releases are published APK-first and manifest-last. The updater verifies trusted HTTPS hosts, APK SHA-256, package name, version code, and the pinned LocalWave signing certificate before installation.
