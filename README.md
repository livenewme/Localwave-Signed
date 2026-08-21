# LocalWave signed release feed

This branch is the live update feed for LocalWave.

- Current version: 0.9.0
- versionCode: 24
- Package: app.localwave.player
- APK SHA-256: f961d6f4234190935a1ae2dc47fe9453340784d8b2f1e9460687c9a171431067
- Signer certificate SHA-256: 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba

v0.9.0 adds Google Cast playback for local music. LocalWave can transfer its queue,
position, playback controls, metadata, and artwork between the phone and Chromecast,
Google TV, Nest speakers/displays, and compatible receivers on the same Wi-Fi network.
Audio stays on the phone and is exposed only through a temporary authenticated local
stream; LocalWave does not upload the library. Google Play services are required, and
receiver codec support varies because LocalWave does not transcode audio.

The updater reads `latest.json`, verifies trusted HTTPS hosts, checks the APK SHA-256,
then validates package name, version code, and signing certificate before installation.
