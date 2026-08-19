# LocalWave Release Security

This repository distributes production-signed LocalWave APKs. It must never contain private signing material.

## Trusted identity

Android package:

`app.localwave.player`

Trusted release certificate SHA-256:

`34d98c603a2a2c54777c0065ecc3e38c3a4162d4f37d09ae137d004654d39a72`

Key algorithm: RSA 3072-bit

## Never commit

Do not commit any of the following:

- `.jks`, `.keystore`, `.p12`, or private-key files
- signing passwords
- recovery passwords
- plaintext signing backups
- CI secrets
- temporary decrypted signing material

## Publication requirements

Before an APK is published here, verify:

1. APK signature is valid.
2. APK is signed by the trusted LocalWave certificate.
3. Package name is exactly `app.localwave.player`.
4. `versionCode` is greater than the previous production release.
5. `versionName` matches the intended release directory and filename.
6. SHA-256 is calculated from the exact final signed APK.
7. The published APK bytes match that SHA-256 after upload.

## Client-side enforcement

The LocalWave updater must independently validate downloaded APKs. Repository ownership, filenames, release notes, and metadata are not sufficient trust anchors by themselves.

The release certificate is the final update-continuity authority.

## Immutability

Once a production version is published, do not replace its APK with different bytes. If a correction is required, publish a new version with a higher `versionCode`.
