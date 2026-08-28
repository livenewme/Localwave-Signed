# LocalWave signed release feed

This branch is the live update feed for LocalWave.

## Current updater release

- Current version: **0.13.32**
- versionCode: **66**
- Package: `app.localwave.player`
- APK SHA-256: `f3551bda7dcb9881af967a3fc7db2ff607351498c633f8c934445cf3626f55df`
- Signer certificate SHA-256: `58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba`

v0.13.32 adds Standard, Weighted, Algorithmic, and Smart / Adaptive shuffle modes with skip/time-context learning while preserving stochastic queue order.

## v0.13.33 / code67 status

A manually signed **v0.13.33 / code67** test candidate exists for Personal bulk metadata editing. It is intentionally **not the live updater release yet**. `latest.json` must remain on v0.13.32/code66 until code67 is physically accepted and subsequently rebuilt/verified through the normal source CI release gate.

Candidate verification metadata is recorded under `releases/v0.13.33/`.

Releases normally follow APK-first / manifest-last publication. The updater verifies trusted HTTPS hosts, APK SHA-256, package name, version code, and the pinned LocalWave signing certificate before installation.
