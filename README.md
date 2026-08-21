# LocalWave signed release feed

This branch is the live update feed for LocalWave.

- Current version: 0.5.3
- versionCode: 19
- Package: app.localwave.player
- APK SHA-256: 9130e67fd8b8f1ac7d6c0e6091c24f99d6fd3a0838bd0e04192303e547d2841d
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba

The updater reads `latest.json`, verifies trusted HTTPS hosts, checks the APK SHA-256,
then validates package name, version code, and signing certificate before installation.
