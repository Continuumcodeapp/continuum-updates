# 0.96.98

The Usage tab is rebuilt. Pick a provider once and every chart on the page follows it, see your spend day by day instead of as one flat number, and for the first time see what each pull request cost you: tokens and dollars per PR, per repo, gathered from every machine in your account and every harness you run.

## Usage, redesigned

- One provider filter scopes the whole tab. Choose All, or Claude, Codex, Gemini, Cursor, Grok, OpenCode or Antigravity, and the gauges, charts, repo list, model list and distributions all narrow to it.
- Your account gauges are one row each, labelled, instead of a wall of tiles. You can read which account is near its limit at a glance.
- Spend is charted day by day at every range, full width, so a spike has a date instead of being averaged away.
- Repo, provider and model sit in one equal-height row, and hovering a slice or a legend entry highlights the same thing in all three.
- Hovers carry real detail now: provider mix for the day, the weekly average behind a bar, and what a number is made of rather than just the number.

## Cost per pull request

- Every session is attributed to the pull request it belongs to, so Usage shows spend and tokens per PR, grouped by repository. Attribution works across Claude, Codex, Gemini, Cursor, Grok, OpenCode and Antigravity, whether the work happened in a branch, a worktree, or a session you opened from a PR link.
- The distribution view puts every PR in a repo on one axis with the median, the mean and the middle half of the range marked, so an unusually expensive PR is obvious instead of hidden in an average. Click a PR to open it.
- It is per account, not per machine. Each of your devices publishes its attribution to your account and the Mac merges the lot, so a PR you worked on from the Linux box and finished on the Mac reads as one cost.

## Faster, quieter

- Usage opens instantly. It serves the history it already has, then fills in the rest as it parses, newest first, with real progress and a time estimate instead of a spinner on an empty page.
- Background CPU while uploading usage is much lower. The collector now reads only what is new rather than re-parsing your entire Codex history on every tick.
- Installing an update no longer throws away your usage history and rebuilds it from scratch.
- A partial read can no longer replace a fuller one, so numbers stop dropping and recovering while a refresh runs.

## Fixes

- The app icon and code signature are correct again. Bundled Python bytecode was breaking the bundle seal, which is what made the icon render wrong on Tahoe. The build now fails rather than shipping an app whose seal is broken.
- Refreshes that only top up recent data are no longer described as a full rebuild.

## Everywhere else

- Web and the Windows and Linux desktop app get the same redesigned Usage tab.
- iPhone and the Android and iOS Expo app get the per-PR module at the same spec.
