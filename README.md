# LocalWave signed release feed

This branch is the live update feed for LocalWave.

- Current version: 0.13.0
- versionCode: 34
- Package: app.localwave.player
- APK SHA-256: ebbcf17df7bc98185b7e42f87b5fef47fa9b8f14d93e517a4dd87d0b22412cea
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba

v0.13.0 integrates an active Samsung/DLNA TV session into the normal LocalWave library/player. The Play on TV screen remains the setup/management surface, while normal playback controls and music selection continue working after returning to the main app. A persistent route banner identifies the connected TV/group.

Releases are published APK-first and manifest-last. The updater verifies trusted HTTPS hosts, APK SHA-256, package name, version code, and the pinned LocalWave signing certificate before installation.
