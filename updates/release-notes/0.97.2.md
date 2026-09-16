# 0.97.2

A Claude account connected from Cloud now keeps working in the Terminal instead of dying a few minutes later, archiving a worktree actually clears it off your disk, and the Browser sits beside the thread as its own pane. Settings looks like one app again.

## Your Claude accounts keep working in the Terminal

- A second Claude account connected from Cloud stays usable from the Terminal. Its wrapper survived one launch and then reported itself signed out a few minutes later; it now follows the credential wherever Claude Code keeps it, and repairs itself in place when there is nothing left to follow.
- An account that has been locked out says so. The row read Connected while every command for it was being refused, because the block was rebuilt from whatever the last sync happened to observe rather than from what was actually recorded.
- Each account keeps one command name. Reconnecting no longer leaves a dead `claude-personal` behind and pushes the live account onto `claude-personal-2`.

## A first-class Browser pane

- Browser is its own pane in the right rail next to Tasks, Code and Terminal, and it can take about 60% of the workbench so a live preview sits beside the thread you are working in.
- Leaving the Browser keeps the width you set for it instead of discarding it.
- The Browser chrome offers only what it can actually do. Two buttons were drawn there that had nothing behind them on this platform.

## Archiving a worktree clears it

- Archiving a Code worktree on Mac moves its Continuum-owned checkout to Trash. Archive used to hide the row without recording anything, so the folders stayed on disk under `~/Clawdmeter/workspaces` and piled up.
- Worktrees hidden by the old path have no durable record. Restore them once and archive again, and the sweeper reclaims what was left behind.

## Settings, as one app

- Every Settings pane uses the same cards and the same toggle. Browser Control was showing a native iOS-style switch next to Continuum's own everywhere else.
- A toggle that is busy cannot be flipped. The cloud-sync switch could still be tapped mid-request and fire a second one.
- A disabled button now reads as disabled instead of looking live and quietly ignoring the click.

## The sidebar tells you what a worktree is

- An open worktree with no pull request shows a git-branch mark, matching Mac and iOS. It was drawing a pull-request mark, which made the branch look like it was already in review.
- Failing checks retint the mark and say so out loud, instead of turning red with nothing said.

## Fixes

- The Usage tab drops the explainer copy under the gauges and the per-PR chart; the numbers were already saying it.
- The model picker no longer repeats the selected model in a footer chip under the list.
- The Mac app builds on the release Xcode again, and a build from a clean checkout no longer fails once on a missing icon before it will run.
