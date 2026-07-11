# Continuum 0.57.0

A Code-tab responsiveness release: sending feels instant, long live sessions no longer freeze mid-turn, worktrees switch on the first click, and session names settle in with a smooth animation - plus account re-login and a batch of sidebar/composer polish.

## New & improved

- **Sending feels instant.** Hitting send in the Code tab now clears the composer immediately and flows your message into the transcript as a "Sending…" bubble that settles into the real turn once it lands - no more echo in the composer chrome. (#731)
- **Animated session names.** When a session's name resolves from its git branch to the AI-summarized title, it now cross-fades smoothly instead of snapping. (#728)
- **Re-login without re-adding.** Logged-out secondary provider accounts (Settings → Providers) now show a one-click "Re-log in" button that re-authenticates the existing account in place. (#730)

## Fixed

- **Long live sessions no longer freeze mid-turn.** On long Claude sessions the transcript could stop updating while a turn was streaming; the live projection is now incremental, so the body keeps rendering no matter how long the session runs. (#732)
- **Worktrees switch on the first click.** Clicking a Code-tab worktree while an agent was editing it used to need a second click; it now registers on the first. (#729)
- **New-session pane stays full-height.** The chat pane no longer collapses (floating the composer toward the center) while a new session is provisioning. (#727)
- **Pointing-hand cursor on "Add project."** The Code sidebar's Add-project (+) button now shows the pointing-hand cursor on hover, matching its neighbors. (#726)

Ships build 271 for Mac (signed Sparkle feed).
