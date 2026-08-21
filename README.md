# LocalWave signed release feed

This branch is the live update feed for LocalWave.

- Current version: 0.7.0
- versionCode: 22
- Package: app.localwave.player
- APK SHA-256: 977da2218c719fc219beec3582e5757a78ed664bb8c406f8cbda63b991782049
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba

v0.7.0 adds Album Metadata Rescue. Complete MP3 CD-rip folders are matched as
whole discs using track order, exact track count, and the full duration sequence.
Every candidate shows confidence and a track-by-track before/after preview before
Android requests write consent. Existing year, genre, and embedded artwork are
preserved and filled only when missing. The single-track fallback now uses
duration and track-position context.

The updater reads `latest.json`, verifies trusted HTTPS hosts, checks the APK SHA-256,
then validates package name, version code, and signing certificate before installation.
