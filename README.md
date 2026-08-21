# LocalWave signed release feed

This branch is the live update feed for LocalWave.

- Current version: 0.10.3
- versionCode: 29
- Package: app.localwave.player
- APK SHA-256: 79a68c819c2d7756bcbee4472355e90fad979286b484dc6f0b9b5e42df6c17f6
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba

v0.10.3 keeps the device-accepted Samsung/DLNA audio route from v0.10.2 and adds receiver-facing album artwork metadata while retaining isolated Google Cast support.

Releases are published APK-first and manifest-last. The updater verifies trusted HTTPS hosts, APK SHA-256, package name, version code, and the pinned LocalWave signing certificate before installation.
