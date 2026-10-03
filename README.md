# LocalWave signed release feed

This branch is the live update feed for LocalWave.

## Current updater release

- Current version: **0.13.38**
- versionCode: **72**
- Package: `app.localwave.player`
- APK: `releases/v0.13.38/LocalWave-v0.13.38-release-signed.apk`
- APK size: **3,086,228 bytes**
- APK SHA-256: `a0b321b4492661a8bc0a415938da46f6da24d6383402956a562927e8c805fe78`
- APK Git blob: `7070240e2bebb00212f1904aeda679618bf35444`
- Signer certificate SHA-256: `58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba`
- Feature source head: `8b4d503b0142f3d5a42bdb5a9e2805babb0198bc`
- Tested PR merge revision: `0996f7031792aba714226b36aa5e4763f60ffb19`
- PR: **#57**
- Build: LocalWave **#357** / run `34744481828`
- Physical-device acceptance: **pending**

v0.13.38 adds Bluetooth participation in Whole House through LocalWave's capability-driven Output Fabric while preserving one Android-owned local playback leg and existing transport isolation. Bluetooth/local + Google Cast mixed playback remains intentionally unsupported in this release because the current Cast adapter transfers the sole player rather than operating in parallel.

Releases follow APK-first / manifest-last publication. The updater verifies trusted HTTPS hosts, APK SHA-256, package name, version code, and the pinned LocalWave signing certificate before installation.
