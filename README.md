# LocalWave signed release feed

This branch is the live update feed for LocalWave.

- Current version: 0.13.1
- versionCode: 35
- Package: app.localwave.player
- APK SHA-256: 3797d42549ed1b2c2446862fa38ac320a0d3ca2cc686524cddf3b68a4c74cb64
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba

v0.13.1 performs a selective DRY cleanup while preserving deliberate isolation between ordinary UI and fragile TV/Cast behavior.

Releases are published APK-first and manifest-last. The updater verifies trusted HTTPS hosts, APK SHA-256, package name, version code, and the pinned LocalWave signing certificate before installation.
