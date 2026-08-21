# LocalWave v0.10.0 Chromecast retry

v0.10.0 is the live LocalWave updater release for physical-device Chromecast testing.

- Package: `app.localwave.player`
- Version: `0.10.0`
- versionCode: `26`
- Size: `2,855,475` bytes
- SHA-256: `bae6fb65bfb1dd4fa84ffcd7ba7ddf69928955818e6fcc411d841d7fefaafafd`
- Source head: `9901217d442df1536b66a1c9bd9874b7d601e57c`
- CI: Build LocalWave run #98
- Signature: APK Signature Schemes v2 and v3; same LocalWave certificate as v0.9.1

This release retries Chromecast behind an isolated opt-in boundary. Normal launch retains the
accepted v0.9.1 local-player startup path. Cast and MediaRouter classes initialize only after the
user taps Cast, and CI checks both source and minified DEX output to keep Cast implementation types
off the normal startup path.

v0.9.0 remains withdrawn. If v0.10.0 exposes another physical-device regression, recovery must use a
new higher versionCode signed with the same trusted LocalWave release identity so it installs over
v0.10.0 without uninstalling or losing app data.
