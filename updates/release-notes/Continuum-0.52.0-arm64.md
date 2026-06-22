# Continuum 0.52.0

A Code-workbench release: a collapsible sidebar, a working Group / Sort / Status funnel, and noticeably smoother transcript scrolling — plus appearance polish.

## New & improved

- **Collapsible Code sidebar.** Collapse the left sidebar to reclaim space — a toggle in the workbench tab row docks it, and it hover-peeks back in as a floating overlay while collapsed (your choice persists). The window also resizes genuinely narrow now; the old 1280px minimum is gone. (#671)
- **Filter & sort the Code sidebar.** The Group by / Sort by / Status funnel is now live for managed sessions: **Status** filters branches (Active / In Review / Done), **Sort by** reorders them (Recency / Created / Name), and non-Repo **Group by** shows flat session groups. (#673)
- **Smoother transcript scrolling.** Long Code-tab transcripts now project incrementally off the main thread, so scrolling stays smooth at 60Hz while a reply streams. (#669)
- **Clearer theme names.** The Appearance theme picker now reads simply **Dark** and **Light**. (#672)
- **Refined send button.** The composer's send button is now a light primary circle that reads as one continuous control with the stop button, and renders correctly in light mode. (#668)
- **Calmer top tabs.** Removed the data-stream animation from the Code top tabs (the sidebar still shows live stream activity). (#661)

Ships build 266 for Mac (signed Sparkle feed).
