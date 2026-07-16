# Continuum 0.63.0

Cloud sessions can now run straight from a GitHub repository — connect an account, pick an authorized repo, and Continuum spins up a managed cloud worker with short-lived, repository-scoped credentials, no local Mac worktree required. Code gets a dedicated live To-dos tab, Continuum Voice keeps running in the background with Action Button and Dynamic Island controls, and the Watch swipes between full provider limit pages. Plus a wide sweep of Mac reliability fixes: accurate animated worktree diff counters, sturdier session recovery, and dependable Grok sends, paste, and stop behavior.

## Features

- **Run Cloud on a GitHub repository.** Turn on Cloud, connect a GitHub account, and choose any authorized repository instead of depending on a local Mac worktree. Private repositories run in managed cloud workers with short-lived, repository-scoped credentials for clone, push, and pull-request creation — tokens rotate as sessions start or wake and are never written into Git config or command history. Cloud startup stays fail-closed until GitHub access and the managed daemon are ready. (#1124, #1125)
- **A live To-dos tab in Code.** Code sessions now have a dedicated To-dos tab before Plan, showing an ordered checklist whose pending, active, completed, blocked, and failed states update as the model works. Claude, Codex, Grok, Antigravity, and ACP-backed models all publish the same provider-neutral checklist, and the Plan tab renders the full Markdown plan document separately from execution to-dos. (#1127)
- **Continuum Voice in the background.** Dictation keeps running when you leave the app, with Action Button and Dynamic Island controls, a Live Activity showing recording state, and a stop control that ends recording from anywhere. Finished transcripts insert at the keyboard or fall back to the clipboard. (#1123)
- **Swipe through provider limits on Watch.** The Watch app swipes between full provider limit pages, each with its own identity and persistent page selection, and complications drop providers you removed on iPhone. (#1122)

## Fixed

- **Worktree diff counts are accurate and animated.** Addition and deletion totals in the Code sidebar tick independently with a quick counter animation (instant under Reduce Motion), and badges now measure the final working-tree snapshot against its default-branch point — so staged or unstaged rewrites and undos are never double-counted. Untracked, binary, encoded, and symlink files follow Git's own diff rules. (#1128)
- **Sturdier session recovery.** The Mac session registry reconciles its JSON snapshot against SQLite on launch, replaying newer receipts over stale snapshots without dropping snapshot-only sessions, keeping failed writes dirty for retry, and never erasing privacy-delete evidence early. (#1121)
- **Reliable Grok sends and queued prompts.** Grok sessions start a second message or Create PR by resuming their exact provider session (surviving an app relaunch), queued prompts dispatch the moment the provider yields even while background work keeps a session streaming, and startup failures now surface the real CLI error. (#1118, #1119)
- **Stop and Send-now work mid-flight.** An explicit Stop or Send-now resolves a held completion locally instead of failing with "Couldn't interrupt the current run" while a Claude turn waits on background work. (#1116)
- **Composer input fixes.** Shift-Return inserts exactly one newline at the caret, and Command-V pastes normally in Mac Chat, Cowork, and Code instead of opening the voice transcriber — conflicting shortcuts repair themselves on launch. (#1112, #1114)
- **Notifications follow the live theme.** Notifications, handoff toasts, and Cowork alerts switch between light and dark palettes while they remain visible. (#1113)
- **Code setup surfaces are clearer.** The Code review pane opens from an empty home, a managed repo without a worktree, or a sessionless worktree and floats over constrained windows; connected Codex providers show ready / needs-auth / needs-install state; and Claude's Re-authenticate refreshes usage and credentials cleanly. (#1110, #1111, #1115)
- **Quieter, cleaner chat.** Claude context compaction renders as a lifecycle event rather than a message, and phone↔Mac pairing is now email-account only. (#1126, #1117)

## Under the hood

- **The cloud backend can run entirely on the owned GCP box.** Postgres-backed adapters can replace Neon and Cloudflare KV/Durable Objects for relay, APNS, and workspace state, with sliding session tokens capped by an absolute lifetime and strict tenant scoping for workspace mirrors. Cutover is a separate, feature-flagged rollout. (#1125)
