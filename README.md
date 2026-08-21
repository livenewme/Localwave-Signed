# LocalWave signed release feed

This branch is the live update feed for LocalWave.

- Current version: 0.11.0
- versionCode: 30
- Package: app.localwave.player
- APK SHA-256: ec1158f059914e65a9be1844f2620375bec0a27e6615fb3c389530559e56d8a4
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba

v0.11.0 adds Samsung/DLNA Whole House playback on top of the device-accepted single-TV audio/artwork path. Users can select multiple discovered TVs and control them as one group with synchronized starts and drift correction. Google Cast remains available as a separate route.

Releases are published APK-first and manifest-last. The updater verifies trusted HTTPS hosts, APK SHA-256, package name, version code, and the pinned LocalWave signing certificate before installation.
