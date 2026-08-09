# Continuum 0.84.0

## What's new

- **A built-in text editor in the Code workspace.** Open any file in the repo a session is working on — fuzzy file finder, tabs, syntax highlighting, find & replace, and ⌘S to save — right beside the terminal and review panes, on Mac, web, and the Windows/Linux desktop app. Saves are safe by design: files round-trip byte-for-byte, and an edit made outside Continuum is never clobbered — you get a conflict prompt instead of a silent overwrite. (#1486)
- **The update chip is back on the Code tab.** It anchors top-right of the tab strip (and the fresh-launch screen), so a pending update is visible from Code again. The browser on/off chip is tucked out of the Code toolbar on Mac — browser selection and the never-automate site list live in Settings → Browser Control. (#1487)

## Fixes and under-the-hood

- Editing the same file from two sessions on one repo keeps each session's undo history separate. (#1486)
- A dirty editor buffer from a deleted session no longer blocks quitting the app. (#1486)
