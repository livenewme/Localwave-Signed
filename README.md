# LocalWave signed release feed

This branch is the live update feed for LocalWave.

## Current updater release

- Current version: **0.13.35**
- versionCode: **69**
- Package: `app.localwave.player`
- APK: `releases/v0.13.35/LocalWave-v0.13.35-release-signed.apk`
- APK size: **3,078,091 bytes**
- APK SHA-256: `1be57cec2abb856743d4e1e53319121606cdb408e6e9b731546feafdaea1fc5b`
- APK Git blob: `a7a64841a9e1af8668aec98cb474fb7773eb0479`
- Signer certificate SHA-256: `58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba`
- Source branch: `codex/audio-engine-v0.13.35`
- Release source head: `a6ff6e99313e51420fd48a2381c8751dac2cd2cc`
- Build: LocalWave **#328** / run `33709145683`
- Publisher run: `33709518045`

v0.13.35 is the LocalWave audio-engine overhaul. It adds ReplayGain-aware Track/Album volume normalization, a private on-device loudness analyzer for untagged music, and a real six-band parametric EQ with adjustable shelf/peak filters, frequency, gain, Q, presets, preamp, automatic headroom, smooth gain changes, and clipping protection.

The DSP engine is deliberately limited to LocalWave's local PCM playback path. Cast, Samsung/DLNA, Roku, and Whole House transports retain their existing isolated transport-native behavior.

## Release integrity

Build #328 passed the selective-DRY boundary guard, launcher/TV startup-isolation guard, JVM tests, Android lint, release/R8/resource shrinking, post-R8 startup isolation, signing, and artifact upload.

The signed APK was independently checked for package/version, ZIP integrity, 16 KiB/page alignment, signer continuity, v2/v3 signatures, size, SHA-256, and Git blob. Publication then staged the exact APK bytes first, re-fetched and verified the public APK, advanced `latest.json` last, verified the final manifest/APK pair, and removed the one-shot publisher.

Releases follow this APK-first / manifest-last process. The updater verifies trusted HTTPS hosts, APK SHA-256, package name, version code, and the pinned LocalWave signing certificate before installation.
