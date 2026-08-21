# LocalWave signed release feed

This branch is the live update feed for LocalWave.

- Current version: 0.8.0
- versionCode: 23
- Package: app.localwave.player
- APK SHA-256: 518f33159f45e344ac81fda2e2b574e9435538c97b606b9e6be52bf8cb5ca40d
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba

v0.8.0 adds private, on-device monthly Listening Statistics: qualified song
plays, actual audible time, top artists and tracks, active days, and the busiest
three-hour listening window. Library Health probable-duplicate results can now
be compared file by file, played, kept, or deleted one selected file at a time
through Android's confirmation flow. Duplicate detection remains probabilistic;
LocalWave never bulk-deletes or silently chooses a file.

The updater reads `latest.json`, verifies trusted HTTPS hosts, checks the APK SHA-256,
then validates package name, version code, and signing certificate before installation.
