# LocalWave Release Archive

Historical LocalWave releases live here for provenance, rollback research, regression comparison, and recovery work.

**The in-app updater does not enumerate this directory.** Production update discovery is restricted to the top-level `releases/` directory.

Archived artifacts are immutable historical records. Never replace an archived APK with different bytes under the same version.

## Historical release index

| Version | SHA-256 |
|---|---|
| v0.2.0 | `30230baa82ac97e501a4ee2d2acbd7ebd051efc596f67a863236f27177a5a124` |
| v0.2.1 | `2c72f65e206b48e7c745b03ef489a7b016fd382b717131eaf217b9cbdb360510` |
| v0.2.3 | `bacecd320da48790cb83e0e94905c83cab36cf0f86ab68e4685b061326702979` |
| v0.2.5 | `9abe0710ddb7aa05ce414013dd7f71af4d456e0be0a29d1cd11a290761d74fae` |
| v0.4.1 | `827ddf04d86d990390c3a1b47f32cab31815069be8d6d9023343115e698c034b` |
| v0.4.2 | `44e9be6420d13399bc525e122ee0e70997617a8d2261e7e3e8a1e1b69dc66fe7` |
| v0.4.3 | `e775fb3f7557cfd472628957d6dcc4355df3dd9790be02f4820e1caae295549e` |
| v0.5.0 | `fcac32c45862a7cd9d595451bb26db076c30757f6772015633a5fc6500451c07` |

All normal-update-compatible APKs must preserve package `app.localwave.player` and the established LocalWave release certificate SHA-256:

`34d98c603a2a2c54777c0065ecc3e38c3a4162d4f37d09ae137d004654d39a72`

Binary APKs may be copied into per-version archive directories as they are recovered. The table above is the durable historical fingerprint index.
