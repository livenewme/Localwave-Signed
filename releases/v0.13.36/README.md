# LocalWave v0.13.36 / code70

Fixes the in-app Change Log so it uses one canonical bundled changelog. The stale `changelog_recent` resource that appeared above newer releases has been removed, and CI now verifies both source and packaged-APK changelog freshness against the app version.

## Release verification

- Build: LocalWave #330
- Run: `33710209484`
- Source head: `52f00111618deb9c2227da9d4c543d3e815a36e8`
- Package: `app.localwave.player`
- versionName: `0.13.36`
- versionCode: `70`
- APK: `LocalWave-v0.13.36-release-signed.apk`
- Size: `3,069,844` bytes
- SHA-256: `9af17d768a4c5aeae389379cfae11571cb3c996142bcb0f700d10e4d20373510`
- Git blob: `7776114ee0e99596a4e7ef8fb4aa5e25df826216`
- Signer certificate SHA-256: `58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba`
- APK Signature Scheme v2: verified
- APK Signature Scheme v3: verified
- Packaged changelog first release: `v0.13.36`
- Retired `raw/changelog_recent`: absent

The exact signed APK was staged and publicly re-verified before `latest.json` was advanced.
