# LocalWave signed release feed

This branch is the live update feed for LocalWave.

- Current version: 0.6.0
- versionCode: 21
- Package: app.localwave.player
- APK SHA-256: d25bdf4f32879dc7327fe8e92524310b1293022e80f84eacaeafb5f4f243ff85
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba

v0.6.0 adds Library Health: a collection score with actionable findings for
missing artwork and tags, probable duplicates, suspiciously low-bitrate audio,
and inconsistent album names. Metadata fixes use LocalWave's consent-based MP3
editor; duplicate and bitrate findings are review-only.

The updater reads `latest.json`, verifies trusted HTTPS hosts, checks the APK SHA-256,
then validates package name, version code, and signing certificate before installation.
