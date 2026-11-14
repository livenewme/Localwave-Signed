# LocalWave signed release feed

This branch is the live update feed for LocalWave.

## Current updater release

- Current version: **0.14.1**
- versionCode: **74**
- Package: app.localwave.player
- APK: releases/v0.14.1/LocalWave-v0.14.1-release-signed.apk
- APK size: **3,090,324 bytes**
- APK SHA-256: c8387187312266f8b463133577b05cfe5e50aa9ae298cc057fc0e564192c7b8d
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba
- Build: LocalWave run 43553075923
- PR: **#60**
- Physical-device acceptance: **pending**

v0.14.1 fixes LAN responses that could stop after the HTTP headers for small payloads. v0.14.0 introduced LAN library sharing: an opt-in read-only JSON index, byte-range audio streams, embedded artwork and mDNS discovery in Outputs.

Releases follow APK-first / manifest-last publication. The updater verifies trusted HTTPS hosts, APK SHA-256, package name, version code, and the pinned LocalWave signing certificate before installation.
