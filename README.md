# LocalWave signed release feed

This branch is the live update feed for LocalWave.

- Current version: 0.10.0
- versionCode: 26
- Package: app.localwave.player
- APK SHA-256: bae6fb65bfb1dd4fa84ffcd7ba7ddf69928955818e6fcc411d841d7fefaafafd
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba

v0.10.0 reintroduces Chromecast behind an isolated opt-in path. Normal LocalWave launch and
local playback retain the device-accepted v0.9.1 startup architecture. Cast/MediaRouter classes
are initialized only after the user taps Cast, and Cast setup failures are contained to the
separate Cast screen rather than becoming a launcher dependency.

The v0.10.0 APK passed the source startup-isolation guard, unit tests, lint, R8/resource shrinking,
release assembly, post-R8 DEX isolation checks, package/version inspection, and v2/v3 signing
verification before activation. It is now intentionally live for physical-device testing.

Release policy: after a build passes the required build, package, signing, and release-feed checks,
it is published as the latest release rather than remaining indefinitely staged for device testing.
If a device regression is discovered after publication, recover with a new higher versionCode using
the same trusted LocalWave signing identity. Never attempt to solve a regression by weakening updater
hash, package, version, or signer validation.

v0.9.0 remains withdrawn after its immediate-launch regression. v0.9.1 remains the accepted recovery
baseline proving that the affected Galaxy S24 Ultra / Android 16 installation can be recovered in
place without uninstalling or losing LocalWave app data.

The updater reads `latest.json`, verifies trusted HTTPS hosts, checks the APK SHA-256,
then validates package name, version code, and signing certificate before installation.
