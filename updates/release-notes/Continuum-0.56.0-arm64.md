# Continuum 0.56.0

A polish + persistence release: your model favorites and provider defaults now survive updates, branches auto-name themselves from your first prompt, and a batch of Code/Chat transcript and composer fixes make the surfaces calmer to read and use.

## New & improved

- **Auto-named branches from your first prompt.** Starting a session now summarizes your opening prompt into a clean branch title instead of leaking raw attachment paths into the name. (#712)
- **Your provider defaults survive updates & reinstalls.** Model, effort, mode, and per-provider preferences now persist across app updates and the bundle-id rename, so you don't re-pick them after every upgrade. (#714)
- **Starred model pairs persist.** Favorite (starred) model pairs and their ⌘1–9 / drag order are remembered across restarts and updates — and you can now star custom and partner models too. (#724)
- **New-tab shortcuts in Code.** ⌘-click the **+** to open a provider/agent new-tab menu, and use ⌘T / ⌘⇧T to open tabs from the keyboard. (#725)

## Fixed

- **Grok usage gauge works again.** The Grok gauge no longer sits stuck at 0% after recent Grok CLI changes — it now reads usage directly from billing. (#711)
- **Attachments stay in your message.** Composer attachments remain inline in the user bubble until the turn completes, instead of jumping to a separate footer strip mid-turn. (#713)
- **No blank second line on short prompts.** Short plain-text prompts like "continue" render as a single line instead of a two-line bubble with an empty tail. (#715)
- **Every transcript-rail tick is hoverable.** Hover and click hit-bands on the right-edge turn rail are now separate, so z-order can't steal hover from a tick. (#716)
- **Cleaner session tabs.** Code session tabs show the title only — the branch subtitle has been removed. (#717)
- **Cleaner edited-file rows.** The grey panel background behind edited-file transcript rows is gone. (#718)
- **No sideways jump when expanding commands.** Expanding a command disclosure no longer slides the transcript horizontally. (#719)
- **Steady edited-file hover preview.** The edited-file hover diff preview no longer flickers or blanks when sweeping quickly across file chips. (#720)
- **Mic next to the +.** The Chat composer's mic button now sits next to the + button. (#721)
- **Archive toast names the branch.** Archiving a worktree session now shows the branch name in the confirmation toast. (#723)

Ships build 270 for Mac (signed Sparkle feed).
