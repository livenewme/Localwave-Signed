# LocalWave signed release feed

This branch is the live update feed for LocalWave.

- Current version: 0.9.1
- versionCode: 25
- Package: app.localwave.player
- APK SHA-256: 5a5b3ba16aea8c3f302192b1a6ea08677e77412cc45ab45a5b541cda044072ea
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba

v0.9.1 is an emergency launch-recovery release. The crashing v0.9.0 build was
withdrawn, and v0.9.1 restores the previously proven v0.8.0 runtime path under a
higher version code so it installs directly over v0.9.0 without uninstalling.
Existing v0.8 features remain available. Chromecast is temporarily disabled while
the v0.9.0 launch crash is investigated.

On 2026-08-21, the affected user installed v0.9.1 directly over the crashing
v0.9.0 build and confirmed that LocalWave launches again on the Galaxy S24 Ultra
running Android 16. Chromecast remains disabled.

The updater reads `latest.json`, verifies trusted HTTPS hosts, checks the APK SHA-256,
then validates package name, version code, and signing certificate before installation.
