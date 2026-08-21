# LocalWave v0.10.0 Chromecast retry

This is a staged direct-install candidate for physical-device testing. The stable updater manifest
intentionally remains on device-accepted v0.9.1 until this build passes cold-launch, Cast discovery,
remote playback, seeking, disconnect, and post-Cast relaunch tests.

- Package: `app.localwave.player`
- Version: `0.10.0`
- versionCode: `26`
- Size: `2,855,475` bytes
- SHA-256: `bae6fb65bfb1dd4fa84ffcd7ba7ddf69928955818e6fcc411d841d7fefaafafd`
- Source head: `9901217d442df1536b66a1c9bd9874b7d601e57c`
- CI: [Build LocalWave run #98](https://github.com/livenewme/LocalWave/actions/runs/32501454881)
- Signature: APK Signature Schemes v2 and v3; same LocalWave certificate as v0.9.1

Install the APK directly over v0.9.1. Android should preserve LocalWave app data because the package
and release signer are unchanged and versionCode 26 is newer than versionCode 25.

Do not point `latest.json` at this APK until the physical-device acceptance checklist in the source
repository's `CHROMECAST.md` passes.
