# LocalWave signed release feed

This branch is the live update feed for LocalWave.

- Current version: 0.5.4
- versionCode: 20
- Package: app.localwave.player
- APK SHA-256: 2c960a6eb069f0f8bb9886f3fd9bd43116de6a84a011feea9f5a06c3a5707629
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba

v0.5.4 is a version-only release for validating the restored updater from v0.5.3.

The updater reads `latest.json`, verifies trusted HTTPS hosts, checks the APK SHA-256,
then validates package name, version code, and signing certificate before installation.
