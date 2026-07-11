# Continuum 0.51.1

A stability release. It rolls back the 0.51.0 transcript-rendering rewrite - which introduced input and scrolling regressions - and fixes two chat issues on top of the restored, stable rendering.

## Fixed

- **The message composer works again.** Rolled back the 0.51.0 transcript-scroll change that could leave the Chat and Code message box unclickable and occasionally blank the transcript after fast scrolling. Input and transcript rendering are back to the stable 0.50.0 behavior. (#663)
- **Steadier Codex turns.** A long-running Codex turn no longer flickers between expanded and collapsed, or fires repeated "session done" notifications, while the model is still thinking. (#665)
- **Code mode stays full-permission.** After an app restart or an idle period, Code-mode sessions no longer pop "Run command?" approval prompts - Code stays at maximum permissions, matching the pill (an explicit Accept-edits choice still asks, as before). (#666)

Ships build 265 for Mac (signed Sparkle feed).
