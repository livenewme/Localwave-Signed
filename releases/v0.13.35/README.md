# LocalWave v0.13.35 / code69

Released 2026-09-02 through the normal GitHub updater path.

## What changed

- Added ReplayGain-aware volume normalization with Off, Track, and Album modes.
- Added a private, cancellable on-device loudness analyzer for tracks without usable ReplayGain; audio is never uploaded and music files are never rewritten.
- Added a true six-band parametric EQ with editable low-shelf, peak, and high-shelf filters, frequency, gain, Q, EQ preamp, and Flat / Bass Boost / Warm / Vocal / Treble presets.
- Added peak-aware normalization limiting, smooth gain ramps, automatic EQ headroom, and final PCM overflow protection.
- Kept the PCM DSP engine local to the phone/wired/Bluetooth/local Android Auto path; Cast, Samsung/DLNA, Roku, and Whole House transports remain isolated.

## Release verification

- Build: LocalWave #328
- Run: `33709145683`
- Source head: `a6ff6e99313e51420fd48a2381c8751dac2cd2cc`
- Package: `app.localwave.player`
- versionName: `0.13.35`
- versionCode: `69`
- APK: `LocalWave-v0.13.35-release-signed.apk`
- Size: `3,078,091` bytes
- SHA-256: `1be57cec2abb856743d4e1e53319121606cdb408e6e9b731546feafdaea1fc5b`
- Git blob: `a7a64841a9e1af8668aec98cb474fb7773eb0479`
- Signer certificate SHA-256: `58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba`
- APK Signature Scheme v2: verified
- APK Signature Scheme v3: verified
- 16 KiB/page alignment: verified

The exact signed APK was staged and publicly re-verified before `latest.json` was advanced.
