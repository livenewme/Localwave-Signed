# LocalWave v0.14.1 signed release

- Package: app.localwave.player
- Version: 0.14.1
- versionCode: 74
- APK size: 3,090,324 bytes
- APK SHA-256: c8387187312266f8b463133577b05cfe5e50aa9ae298cc057fc0e564192c7b8d
- Signed with the existing LocalWave release identity (certificate SHA-256 58d7c6616a809d769b4211cb21a16d37a018a112617184e2f4093cedfeb3e4ba).
- Built and signed by Build LocalWave run 43553075923.

v0.14.1 fixes LAN library responses that could stop after headers for small payloads. /health, small JSON, artwork and short streams now flush before the connection closes.
