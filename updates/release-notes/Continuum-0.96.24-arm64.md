# Continuum 0.96.24

Provider-account hotfixes for a cleaner menu bar and reliable workspace sync.

- **OpenCode now has exactly one menu-bar item.** The Usage-tab toggle governs it across local and hosted accounts, so hosted accounts no longer create duplicate status items. (#1739)
- **Revoked custom providers disappear cleanly after an upgrade.** Continuum retires revoked accounts even when their old local record has no links or blocks, removing ghost `▯ -` menu-bar icons and stopping reconnect loops. The cloud account list can expose tombstones when explicitly requested. (#1740)
- **Revoking a secondary provider identity no longer stalls workspace sync.** Workspace publishes skip the revoked identity instead of failing with a conflict, so the host publisher keeps advancing. (#1741)
- **Release delivery is more dependable.** The obsolete appcast-mirror workflow is retired, PostgreSQL adapter proofs now run against real PostgreSQL in CI, and signed Mac tests stay isolated from the live Continuum app. (#1738)
