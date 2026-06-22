# Continuum 0.53.0

A chat-consistency release: every provider now renders through one shared chat surface, plus a unified titlebar, snappier turn state, and a batch of Code-workbench and iOS fixes.

## New & improved

- **One consistent chat surface across every provider.** Claude, Codex, Cursor, Grok, and OpenCode now render through a single shared renderer with unified turn state, so messages, tool runs, and "thinking" rows look and behave the same no matter which model you're talking to. Claude's normalized segmentation is now on by default. (#683, #684, #685, #686, #687, #689)
- **Unified Mac titlebar with Pair with iPhone everywhere.** One full-width titlebar chip across Chat, Code, and Usage, with the "Pair with iPhone" button now available on all three tabs. (#674)
- **Turn duration in the Code footer.** Completed turns now show how long the turn actually took (e.g. `1m 23s`) instead of a vague "time ago" stamp. (#681)
- **Snappier Stop ↔ Send.** When a turn ends, the composer button and activity indicator now flip immediately instead of lagging up to ~100ms behind. (#675)
- **iOS keyboard & chat polish.** Swipe down anywhere to dismiss the keyboard, the Chat empty-state logos now mirror the Mac (only the providers you've selected), and the Settings → Sessions section is tidied up. (#679)
- **Calmer sidebar streaming.** The worktree stream animation now flows behind the diff counters instead of stopping short, with no dead patch under the badges. (#662)

## Fixed

- **Model picker no longer strands mid-provisioning.** Switching model/provider while a worktree is still provisioning now converges the live runtime to your pick, so the chip and what's actually running can't disagree. (#676)
- **Sidebar rows stop reshuffling.** Code-sidebar worktree rows now hold a stable creation order instead of jumping around on every model turn. (#677)
- **Create PR button stops lingering.** The Code titlebar no longer keeps offering "Create PR" after a PR already exists, and recovers cleanly from a transient daemon hiccup. (#680)
- **Claude session retry recovers.** A failed Claude session now resumes from its live session id, falling back to a transcript hand-off when needed, instead of losing the thread. (#682)
- **Consistent Code permissions.** Code sessions now reliably run with approvals bypassed across every provider, so a Code chip can't decay into permission prompts. (#678)

Ships build 267 for Mac (signed Sparkle feed).
