# Continuum 0.57.20

Cowork connectors grow up: a self-hosted app catalog replaces manual middleware endpoints.

## New

- **Connector app gallery.** Settings → Connectors is now an app catalog on Mac and iOS. Connect GitHub, Slack, Notion, and Salesforce by pasting a token — no middleware account, no "endpoint + API key" plumbing.
- **Self-hosted connector servers.** Each connected app runs its own bundled MCP server on your execution host (your Mac or a Linux box), and OAuth happens directly with the provider — your tokens never transit a third-party service.
- **⌘2 jumps to Cowork.** The Cowork surface gets a dedicated keyboard shortcut alongside Chat and Code.
- **Coming soon: Gmail, Google Calendar, Google Drive, Linear.** OAuth scaffolding is in place; these light up once client registration completes.

Ships build 291 for Mac (signed Sparkle feed).
