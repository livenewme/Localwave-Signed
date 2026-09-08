# LocalWave signed release feed

This branch is the live update feed for LocalWave.

## Current updater release

- Current version: **0.13.37**
- versionCode: **71**
- Package: `app.localwave.player`
- APK: `releases/v0.13.37/LocalWave-v0.13.37-release-signed.apk`
- APK size: **3,086,228 bytes**
- APK SHA-256: `96fa9601de8b0c28f512886e7d9051519d782ae2c34266e9e6710c618bc7b4e3`
- APK Git blob: `c02c737050b8024b82e880cc1deceaa3dcf83b40`
- Signer certificate SHA-256: `58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba`
- Source branch: `codex/backup-consolidation-v0.13.37`
- Release source head: `7dbc7eee2eaac3ae4b06a05b24a8a61a7e29e14e`
- PR: **#56**
- Build: LocalWave **#337** / run `34197450742`

v0.13.37 adds LocalWave Backup & Restore and explicitly-consented Data Consolidation. Consolidation organizes visible MediaStore music into clean Artist/Album folders without rewriting audio/tag bytes, skips ambiguous metadata, resolves filename collisions safely, and hard-excludes Shadow Realm tracks at multiple independent checks.

Releases follow APK-first / manifest-last publication. The updater verifies trusted HTTPS hosts, APK SHA-256, package name, version code, and the pinned LocalWave signing certificate before installation.
