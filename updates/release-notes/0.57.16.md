# Continuum 0.57.16

A reliability fix for the local agent server, so a port conflict is diagnosable instead of a dead end.

## Fixed

- **Clearer errors when the agent server can't start.** If a port in the daemon's range is taken, Continuum now names the process actually holding it - almost always a second copy of Continuum (e.g. a leftover Xcode debug build) - with a "quit it and relaunch" hint, instead of a generic "all ports in use." It also distinguishes a genuine port conflict from other network failures rather than blaming the ports. (#841)

Ships build 287 for Mac (signed Sparkle feed).
