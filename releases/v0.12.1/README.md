# LocalWave v0.12.1

Samsung/DLNA receiver-backpressure repair after physical Q80CA testing exposed repeated HTTP 500 responses under v0.12.0 control polling.

- Position polling reduced from ~350 ms to a receiver-friendly ~850 ms base rate
- Steady-state transport polling decimated to ~2.5 seconds
- Per-TV HTTP 429/500/503 backoff up to 5 seconds with gradual recovery
- Transient busy polling responses no longer flash playback errors
- Adaptive hold Pause aborts quietly when the receiver is busy
- Busy hold resume gets bounded retries
- v0.12.0 master clock, learned latency, artwork, Cast, and startup isolation preserved
