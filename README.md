# LocalWave signed release feed

This branch is the live update feed for LocalWave.

- Current version: 0.10.2
- versionCode: 28
- Package: app.localwave.player
- APK SHA-256: b8ac8988a9b07e3364fd546a231830fae1f7ab974f5277070a235083bef75a7d
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba

v0.10.2 keeps the isolated Google Cast implementation and adds Samsung/DLNA TV discovery and direct local playback through standard SSDP/UPnP AVTransport. The initial hardware target is the Samsung TU690T family.

Releases are published APK-first and manifest-last. The updater verifies trusted HTTPS hosts, APK SHA-256, package name, version code, and the pinned LocalWave signing certificate before installation.
