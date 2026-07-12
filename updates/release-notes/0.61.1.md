# Continuum 0.61.1

A focused Usage-tab cleanup: the two redundant full-width Grok panels are gone, so the tab reads tighter and Grok's numbers live where every other provider's do.

## Fixed

- **The Usage tab drops its two redundant Grok panels.** The full-width Grok token strip that sat between the provider gauges and the Analytics band, and the separate "Grok activity" breakdown below the spend charts, are both removed — they duplicated totals already shown in the gauges, the spend charts, and the Tokens-by-model table. Grok now appears in the gauge column and ranks in Tokens-by-model like Claude, Codex, and the rest, so the tab is shorter and less repetitive with no loss of information. (#1065, #1066)
