# LocalWave signed release feed

This branch is the live update feed for LocalWave.

- Current version: 0.10.1
- versionCode: 27
- Package: app.localwave.player
- APK SHA-256: fb0399d4a8b0bef44909da07d29cf9b86043e4fc7332b480a39b9f8cd922b861
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba

v0.10.1 fixes the first physical-device failure found in the isolated Chromecast retry. v0.10.0 launched normally but AndroidX MediaRouter rejected a missing AppCompat theme color as transparent. v0.10.1 gives only the Cast activity a fully opaque AppCompat-compatible theme and leaves normal LocalWave startup on the previously accepted path.

The updater reads `latest.json`, verifies trusted HTTPS hosts, checks the APK SHA-256, then validates package name, version code, and signing certificate before installation.
