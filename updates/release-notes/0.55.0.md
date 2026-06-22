# Continuum 0.55.0

A Code-tab speed + transcript-readability release: session switching is now near-instant, completed turns read in chronological order with thinking and tools in place, and the new-session sheet is model-first — plus a batch of sidebar/composer polish.

## New & improved

- **Near-instant Code-tab session switching.** Toggling between recently-open sessions is now a sub-250ms visibility flip instead of a full transcript rebuild — a small pool of recent sessions stays mounted, so switching no longer feels frozen. (#707)
- **Readable completed transcripts.** A finished turn now renders its full body in chronological order — thinking one-liners and grouped tool runs shown in place — instead of collapsing everything into a single "Ran N commands" capsule. Collapsing is still available per-turn, and a tap expands any "Thinking" row to the full reasoning. (#703)
- **Model-first new-session sheet.** The Mac new-session sheet is redesigned around picking your model first (Model → Plan/Code → Project), with an Advanced setup-script disclosure. (#706)

## Fixed

- **Every transcript-rail tick is hoverable.** The right-edge turn rail's hit targets used to overlap, so only the newest tick responded to hover/click; each tick now has its own band, so you can hover and jump to any prompt in the session. (#708)
- **Backgrounded sessions show a visible stream.** A session still streaming on a row you've clicked away from now shows a clearly-visible grey data-stream cable instead of an almost-invisible whisper. (#709)
- **Attach is first in the Chat composer menu.** The Chat-tab composer's "+" menu now lists Attach first. (#704)
- **Polished first-run onboarding + Code sidebar.** The onboarding sheet and Code sidebar now match the design system (Tahoe tokens/spacing), and empty states fill the pane. (#705)
- **Clearer empty Code sidebar.** The no-repos subtitle is now the tighter "Add your first repo." (#710)

Ships build 269 for Mac (signed Sparkle feed).
