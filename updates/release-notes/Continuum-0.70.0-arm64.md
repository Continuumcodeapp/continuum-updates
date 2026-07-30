# Continuum 0.70.0

## Fixes
- Worktree sessions no longer lose your opening message or stall before the provisioning trail appears — including on pinned secondary accounts, which now spawn on the fast path and bill the account you actually picked (#1343, #1348)
- Sessions pinned to a secondary Claude account now resolve their transcripts from that account's own project files, and never fall back to another account's history (#1343)
- The composer's effort chip sticks: picking Grok + High stays on High after you send, persists as that provider's default for new sessions, and mid-session effort changes on a live session no longer rewrite your provider-wide default (#1340)
- The sidebar diff badge no longer vanishes on worktrees an agent is actively writing to — counts appear and tick while work happens (#1346)
- An expanded sub-agent row now shows the real prompt it was given and the report it returned, instead of "pending" / "completed" — on Mac, web, and mobile (#1345)
- PR-creation confetti fires reliably — exactly once per created PR, and never for a PR you merely opened (#1350)
- Signing out on the web now actually lets you switch Google accounts instead of silently signing you back in (#1351)
- The web titlebar's Live/Demo pill is gone, matching the Mac and iOS chrome (#1338)

## Features
- The homepage model picker is now the app's real ModelTray — provider rails, favourites, search, and keyboard flows, fed by the live free-model roster (#1341)
- Bundled compute now has end-to-end lifecycle telemetry with a strict privacy allowlist (never prompts, code, or credentials), so a failed cloud-session start can be traced to the exact broken step — plus cleanup compensation so a lost create response can't leave a stray billable lease (#1334)

## Under the hood
- The sessions list no longer ships full plan documents on every poll; plan bodies hydrate on demand and the Approve tray is driven by the authoritative flag (#1335)
- CI now runs on self-hosted runners
