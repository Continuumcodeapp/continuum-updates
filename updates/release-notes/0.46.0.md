# Continuum 0.46.0

A workbench-polish release: smoother streaming chat, branch names taken from your first prompt, a provider chooser for Land PRs, and a sweep of Settings and composer refinements.

## New & improved

- **Branch names from your first prompt.** New Code sessions now name their worktree branch after what you actually asked for (a clean, git-safe slug of your first message) instead of a random city — and rename the live branch once you send, keeping the worktree path stable. (#588)
- **Pick who lands your PRs.** The Land PRs action gets a provider + model + effort chooser, so you can run it on Claude, Codex, Cursor, or any configured agent instead of always Claude. (#582)
- **Smoother streaming chat.** Transcripts now auto-follow the streaming reply with a coalesced glide instead of snapping on every token, and respect Reduce Motion. (#579)
- **Transcripts come back after a restart.** Code-tab chat history for harness sessions (Codex/Cursor/etc.) is restored on relaunch instead of opening blank. (#580)
- **Settings that feel clickable.** Every Mac Settings control gets a pointing-hand cursor and hover highlight, and the groups sidebar is compacted to a tidy icon + header. (#584, #577)
- **A livelier jump-to-latest button.** The jump-to-latest chevron gets a hover wash, a subtle lift, and a pointing-hand cursor. (#573)

## Fixes

- **Cleaner answer copy.** Chat V2 consolidates the answer-copy controls down to a single bottom-left button per turn. (#581)
- **Voice dictation lands in the right field.** Dictating while Continuum is frontmost now pastes into the actual focused field, with a clipboard safety net if delivery can't be confirmed. (#583)
- **Search finds your words.** Chat search now indexes the real message prose (not tool/metadata noise) and is hardened against odd characters. (#585)
- **Steadier working indicator.** The "working" indicator and elapsed timer stay up for the whole turn instead of flickering between tokens. (#574)
- **Composer & transcript polish.** The gutter tick no longer drifts onto your sent message, the turn rail packs into a tidy top-right stack, the mic reads as clickable, the titlebar pane toggle is a clean bare icon, and the empty-state placeholder now reads "Build something special." (#572, #576, #575, #578, #586)

Ships build 258 for Mac (signed Sparkle feed). The iOS app ships the same chat and workspace improvements via TestFlight.
