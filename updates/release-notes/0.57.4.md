# Continuum 0.57.4

A fast follow-up: snappier chat, richer Markdown formatting, and — most importantly — a fix so existing installs can find updates again.

## Fixed

- **Auto-update works again.** The in-app updater was checking an address that went offline when the project moved, so shipped 0.57.3 builds couldn't find new versions (it surfaced as "Appcast signature failed"). It now polls the live update feed, so existing installs will pick up this and every future release.
- **No more workbench crash on the Code tab.** A non-finite or corrupt saved pane width could crash session selection; pane widths are now sanitized and a failed state-save degrades gracefully instead of taking down the tab. (#762)
- **Checkpoints work in a brand-new repo.** Creating a checkpoint in a repository that has no commits yet now seeds an initial commit cleanly — without consuming or disturbing your staged files. (#761)

## Improved

- **Faster chat, especially long conversations.** Chat transcripts mount faster and repaint less when you open a session or scroll, so large conversations feel responsive instead of heavy. (#762)
- **Richer Markdown in chat.** Field-group values, inline data (paths, metrics, IDs, status chains), and tables now render as clean structured chips and grids instead of raw text, with more comfortable line spacing throughout. (#761)
- **Copy gives you just the answer.** Copying an assistant reply now returns the final answer text only, dropping progress-note preambles. (#761)
- **Background indexing respects protected folders.** File indexing and search stay out of your Desktop, Documents, and Downloads, avoiding surprise system permission prompts. (#761)

Ships build 275 for Mac (signed Sparkle feed).
