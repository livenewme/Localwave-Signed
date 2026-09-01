# LocalWave Signed Releases

Public distribution repository for LocalWave signed APKs and the in-app updater feed.

Canonical application source is maintained separately in `livenewme/LocalWave`.

## Updater contract

The Android app reads only:

`release-feed/latest.json`

That manifest points to the exact signed APK and records its version and SHA-256. Release publication must remain fail-closed:

1. publish the exact verified signed APK first;
2. verify the public APK bytes/hash;
3. update `release-feed/latest.json` last.

Do not rewrite published release history or change the LocalWave signing identity merely to reorganize this repository.

The `main` branch is intentionally minimal and human-facing. Updater artifacts live on `release-feed`.
