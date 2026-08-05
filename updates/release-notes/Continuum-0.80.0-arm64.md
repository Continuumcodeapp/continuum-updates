# Continuum 0.80.0

## What's new

- **GPT-5.6 Luna and Terra just got a lot cheaper — everywhere.** OpenAI's August 4 price cut (Luna down ~5x on input) is now reflected on every cost surface: the Usage tab, the composer cost ticker, hosted billing, and the Linux/Windows agent. Your pre-cut history stays priced at the old rates, so past spend doesn't silently rewrite itself. (#1428)
- **The model picker now shows what your plan actually includes.** Locked models stay visible with an Upgrade button instead of pretending to be free — and a signed-in Claude CLI no longer merchandises the whole Claude lineup as "Included in Free". Free accounts get a real lane: the $0 hosted models, plus GPT-5.6 Luna as a budget-capped starter model. Ships on Mac, iOS, web, and mobile. (#1429)
- **Action Button voice on iOS now visibly works.** Press it and the Dynamic Island shows a live green waveform that reacts to your voice, honest delivery states replace the silent clipboard fallback, "Toggle Continuum Voice" appears exactly once in Shortcuts and Spotlight, and the whole path is logged for diagnosis. (#1421)
- **OpenRouter and Z.ai connect by pasting a key.** No OpenCode sign-in, no terminal — the key panel opens right under the provider card and saving the key enables the models in every picker. (#1427)
- **Code mode now skips permission prompts on every provider, including OpenCode** — and each approval is scoped to that one request, so a Code session can never quietly widen what a Plan session is allowed to do. The permission card also finally follows your light/dark theme on every platform, and names the vendor you actually picked. (#1422)
- **Comp grants now send the invite email with the tier's concrete limits.** (#1425)

## Fixes and under-the-hood

- The low-battery / sleep auto-handoff banner is gone. Handoff stays one right-click away ("Continue on…"). (#1423)
- The Claude row's terra-cotta accent bar in Save Costs no longer paints over the label. (#1424)
- Runbook for back-filling comp-grant emails post-deploy. (#1426)
