# Continuum 0.57.10

A reliability-focused release: new sessions start instantly and stop double-sending, the Code/Plan toggle and Grok follow-ups work again, and Code mode now always runs with full permissions. Plus the foundation for per-device host trust.

## New

- **Code mode always runs with full permissions.** A Code session now launches in bypass-permissions mode for every provider, regardless of per-repo trust - there's no separate "trust this repo for autopilot" gate to clear before Code can run unattended. Plan mode still never auto-approves, so Plan continues to prompt before acting. (#810)

## Improved

- **New Session "Create" dismisses instantly.** Clicking Create on the New Session card now hands off to a live, animating session row in well under a quarter-second instead of blocking the card while the worktree provisions and the CLI cold-starts - and your typed prompt is delivered as the first turn the moment the session is ready. (#808)
- **Progress notes read like the conversation.** Codex/Conductor progress notes now render inline as normal model messages instead of being tucked behind a collapsed "N progress notes" disclosure, so you can follow an agent's commentary as it works. (They're still excluded from copy/answer selection.) (#809)

## Fixed

- **New Claude sessions stop double-sending.** Starting a new SDK-backed Claude session and sending your first message no longer renders the "You" bubble twice - the transcript now shows your message exactly once. (#805)
- **Code/Plan toggle works on SDK Claude.** Toggling a default SDK-backed Claude session between Code and Plan (or changing model/effort) now reconfigures it through the agent harness instead of failing with a bogus "Could not locate agent binary on PATH." Starting a new session in Plan also correctly launches approval-prompting rather than silently bypassing. (#812)
- **SDK-Claude turns no longer false-complete or stall out.** When a Claude turn spawns a sub-agent or a `run_in_background` command that goes quiet on the wire while still working, the turn no longer ends early ("session done") or force-fails ("turn went unresponsive") - active background work keeps the turn alive. (#811)
- **Grok follow-ups go through.** A follow-up to a completed Grok turn is no longer spuriously blocked by stale turn state; a genuine mid-turn steer is still correctly rejected. (#807)
- **PR + Merge controls stick when you toggle back to a worktree.** Switching away from a worktree session and back no longer flashes "Create PR" for a branch that already has one (which risked a duplicate PR) - the PR number and Merge button now appear immediately from cache. (#806)

## Under the hood

- **Account-Mesh host trust foundation.** Groundwork for per-device approval/revoke of which devices may control a Mac host, plus iOS host discovery - fail-closed and entirely flag-gated OFF, so behavior is unchanged in this build. (#813)

Ships build 281 for Mac (signed Sparkle feed).
