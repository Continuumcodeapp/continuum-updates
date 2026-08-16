# Continuum 0.92.0

## Features
- Starting a session now shows real setup progress: the trail walks worktree → files → setup → agent as each step actually completes, instead of sitting at 0/4 and snapping to done. Works from the phone, web, and desktop against both Mac and Linux/Windows hosts (#1556)
- Cursor usage now shows its two real rails — Auto and API — with the billing-period total and reset timer on iPhone, matching the Mac, and the Cursor model list recovers on its own after a transient sync failure instead of staying stuck on Auto (#1555)

## Fixes
- A refused session request now tells you why: both hosts return a plain-language reason for every rejected request and log which refusal fired, so "Server returned HTTP 400" dead-ends are gone. The analytics helper also no longer fails on every run, removing a steady source of background load (#1558)
- A shell script arriving in a tool call's title no longer inflates the label into a full-height blob behind the chat transcript — commands are recognized by shell syntax and the label clamps to one line on every client (#1557)
