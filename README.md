# LocalWave signed release feed

This branch is the live update feed for LocalWave.

## Current updater release

- Current version: **0.14.0**
- versionCode: **73**
- Package: app.localwave.player
- APK: releases/v0.14.0/LocalWave-v0.14.0-release-signed.apk
- APK size: **3,090,324 bytes**
- APK SHA-256: 3505e88b8aee17251bafc4d7c158aaae805b2ea6b42a3d867422d465cf40d40d
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba
- Build: LocalWave run 43551624819
- PR: **#59**
- Physical-device acceptance: **pending**

v0.14.0 adds opt-in LAN library sharing in Outputs. While enabled, the visible library is served read-only at /api/library, audio streams at /stream/{id} with byte ranges, embedded artwork at /artwork/{id}, and the service is advertised over mDNS as _localwave._tcp. Sharing is off by default, runs in a foreground service with a Stop action, and never leaves the local network.

Releases follow APK-first / manifest-last publication. The updater verifies trusted HTTPS hosts, APK SHA-256, package name, version code, and the pinned LocalWave signing certificate before installation.
