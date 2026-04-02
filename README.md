# Beeper Chat Network Support Matrix

Interactive "nutritional label" showing what features Beeper supports for each chat network.

## What this is

A single-page HTML tool that lets users select a chat network and see:
- **Baseline features** that work on almost every network
- **Network-specific features** with support status
- **History import details** (how much message history gets pulled in per network)
- **High-impact gaps** where native app users might expect something Beeper can't deliver

## Hosting

This is designed to be hosted on GitHub Pages and embedded in [help.beeper.com](https://help.beeper.com) via iframe:

```html
<iframe src="https://YOUR_USERNAME.github.io/beeper-support-matrix/"
  style="width:100%;height:800px;border:none;"></iframe>
```

## Updating the matrix

All data lives in `index.html` in three JavaScript objects:

- `matrix` — feature support status per network (`yes`, `no`, `partial`, `oneway-in`, `oneway-out`, `na`)
- `historyDetails` — per-network description of how much message history imports
- `highImpactByNetwork` — features to flag as expectation gaps per network

Edit those objects and push. The page updates automatically.

## Data sources

- [Beeper Chat Support Matrix](https://help.beeper.com/en_US/quick-references/beeper-chat-support-matrix)
- [Chat Network History Import](https://help.beeper.com/en_US/chat-networks/history-import)

## Design decisions

- No red anywhere. "Not supported" uses strong amber, "Partial" uses light amber. The tone is "heads up" not "danger."
- Dark mode supported via `prefers-color-scheme`.
- Zero dependencies. Single HTML file, no build step.
