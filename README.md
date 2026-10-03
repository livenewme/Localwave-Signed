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

## Next verified release candidate

**v0.13.38 / code72** is the next release candidate. It is verified but is **not the live updater release yet**.

- Package: `app.localwave.player`
- versionName: **0.13.38**
- versionCode: **72**
- Feature source head: `8b4d503b0142f3d5a42bdb5a9e2805babb0198bc`
- Tested PR merge revision embedded in APK: `0996f7031792aba714226b36aa5e4763f60ffb19`
- PR: **#57**
- Build: LocalWave **#357** / run `34744481828`
- Signed artifact ID: `10313582655`
- APK size: **3,086,228 bytes**
- APK SHA-256: `a0b321b4492661a8bc0a415938da46f6da24d6383402956a562927e8c805fe78`
- APK Git blob: `7070240e2bebb00212f1904aeda679618bf35444`
- Signer certificate SHA-256: `58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba`
- APK Signature Schemes: **v2 + v3 verified**
- Independent artifact verification: **passed**

The v0.13.38 candidate adds Bluetooth participation in Whole House through LocalWave's capability-driven Output Fabric while preserving the single Android-owned local playback leg and existing remote transport isolation.

The exact candidate must not be rebuilt or substituted. Publication remains APK-first / manifest-last: stage the exact verified APK bytes, publicly re-verify size/SHA-256/Git blob/signing identity, then update `latest.json` last. Until that happens, `latest.json` intentionally remains on v0.13.37/code71.

Releases follow APK-first / manifest-last publication. The updater verifies trusted HTTPS hosts, APK SHA-256, package name, version code, and the pinned LocalWave signing certificate before installation.
