# LocalWave v0.13.1

versionCode: 35

SHA-256: `3797d42549ed1b2c2446862fa38ac320a0d3ca2cc686524cddf3b68a4c74cb64`

v0.13.1 is a selective-DRY maintenance release. It centralizes local search, playlist/queue prompt plumbing, row artwork loading, and row duration presentation while deliberately preserving isolation where sharing would couple fragile features. The TV activity now owns independent window/inset chrome, receiver artwork remains separate from local UI artwork, and CI enforces those boundaries.
