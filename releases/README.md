# Signed Release Storage

Production APKs are stored in immutable version directories under this folder.

Expected structure:

```text
vX.Y.Z/
  LocalWave-vX.Y.Z.apk
  release.json
```

The first release intended for this repository is v0.5.1.

Do not place unsigned APKs, signing keys, passwords, source archives, or temporary build artifacts in this directory.
