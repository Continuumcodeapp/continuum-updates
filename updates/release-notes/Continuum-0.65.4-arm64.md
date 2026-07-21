# Continuum 0.65.4

A safer quit and steadier Cursor sessions on Mac.

## New

- **Quit asks before it interrupts work.** Continuum now confirms before quitting while agent
  tasks are still running, so you don't lose an in-progress session by reflex. (#1250)

## Fixed

- **Cursor sessions honor the model you picked.** ACP (Cursor/Grok) sessions now stay pinned to
  the model you selected instead of silently falling back to Auto. (#1249)
