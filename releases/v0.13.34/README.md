# LocalWave v0.13.34 / code68

Released 2026-09-01 through the normal GitHub updater path.

## What changed

- Faster local-library search by caching normalized searchable song metadata instead of repeating normalization work for every row on every keystroke.
- Faster artwork scrolling by coalescing concurrent embedded-cover requests for the same MP3 into one extraction/decode operation.
- Added a bounded negative cache for tracks with no embedded artwork, avoiding repeated `MediaMetadataRetriever` work while scrolling.
- Preserved recycled-row safety and edit-safe artwork invalidation.
- Includes Personal bulk metadata editing from v0.13.33, now rebuilt through the normal Gradle/R8 release path rather than the earlier manual code67 exception.
- Fixed the inherited code67 custom-button AppCompat lint issue without suppressing lint.

## Release verification

- Build: LocalWave #323
- Package: `app.localwave.player`
- versionName: `0.13.34`
- versionCode: `68`
- APK: `LocalWave-v0.13.34-release-signed.apk`
- Size: `3,057,611` bytes
- SHA-256: `edaeece9cf5e8751c73866125c79664957fd196f495eea342707bdb5fabcf7a4`
- Git blob: `4b92834d666c669c72723247a4d43dddd7118e70`
- Signer certificate SHA-256: `58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba`
- APK Signature Scheme v2: verified
- APK Signature Scheme v3: verified

The exact signed APK was staged and publicly re-verified before `latest.json` was advanced. v0.13.34/code68 is the current live updater release.
