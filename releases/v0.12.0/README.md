# LocalWave v0.12.0

Adaptive Whole House clock synchronization for Samsung/DLNA televisions.

- Phone-side authoritative monotonic track clock
- Per-TV adaptive software clocks from repeated DLNA position observations
- Network RTT midpoint timestamp correction
- Persistent learned Play-to-playing latency per television
- Staggered starts so slower TVs are commanded earlier
- ~350 ms active timing sampling
- Sub-second correction by briefly holding early TVs instead of coarse fractional seeks
- Late-TV master-clock rendezvous
- Google Cast, single-TV DLNA, metadata/artwork, and startup isolation preserved
