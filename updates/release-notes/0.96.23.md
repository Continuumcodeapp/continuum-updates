# Continuum 0.96.23

The reliability release: 20 fixes so every device stays in sync, plus a Mac crash fix.

- **The Mac no longer crashes while you dictate.** Composer layout updates are deferred out of AppKit's layout pass, closing a crash that fired on nearly every dictation session, fast typing burst, and IME composition. (#1737)
- **Your sessions reach every device again.** A single malformed provider row could silently reject a computer's whole sync upload for hours; bad rows are now skipped and reported instead, and archives use the publish clock so a long tool call can't archive a live session. (#1722, #1717, #1719)
- **No more "preferred" computer.** iPhone, web, and the desktop apps now connect to all of your online computers at once and show the union of their sessions: sleeping one machine only pauses its own rows instead of the whole app. (#1728, #1732)
- **Steer a running turn reliably.** Mid-turn messages now steer every provider, including Grok; if delivery fails they retry as a steer instead of silently queueing, and very large transcripts no longer kill the connection. (#1729, #1733)
- **Photos and files actually arrive.** A send with attachments is projected once and delivered with its attachments; queued attachment sends survive an app restart. (#1724)
- **Sign-in heals itself.** Mac and mobile recover your account from the saved credential after a reinstall or lost cache, duplicate computer entries are cleaned up safely, and a device's "online" state now reflects a real control connection. (#1726)
- **Usage gauges tell the truth.** Expired rate-limit windows from an idle computer can no longer resurface as live limits, and one account per identity is shown even when it's connected on several devices. (#1727, #1731)
- **Faster reconnects.** Phones detect a dead connection in seconds instead of a minute, relay handoffs can't deliver a stale connection, and remote commands use the correct per-endpoint time budgets. (#1725, #1720)
- **Free lane: Muse Spark 1.2** is available unmetered across all clients.
