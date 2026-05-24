# VolcanoActivityTerminal

Terminal-style Monte Carlo dashboard for active volcanoes with VEI eruption probability sims, hazard heat-matrix, and volcanology-community chatter sentiment.

## Features

- **Monte Carlo simulation** — Geometric Brownian Motion engine, configurable paths (100 / 1k / 10k) and horizons (5 / 30 / 90 / 252 periods).
- **Volcano watchlist** — 12 volcanoes (SAKU, KILA, ETNA, STROM, FUEGO…).
- **Live tick simulation** — synthetic ticks every few seconds with deterministic seed for reproducibility.
- **Strategy signals** — ERUPT / DORMANT / WATCH derived from Seismic MA Cross, Inflation MR, Tremor Momentum, VEI Skew, Volcanologist Notes.
- **VAT chatter panel** — positive / neutral / negative sentiment with sample posts per volcano.
- **Volcano KPIs** — aggregate value, P&L, expected return, 95% VaR, Sharpe, sentiment.
- **Custom panel** — VEI × thermal-anomaly hazard heat-matrix with glyph + color severity.
- **Accessible by default** — WCAG 2.2 AA: keyboard nav, ARIA live regions, screen-reader chart alternatives, 4.5:1 contrast in dark mode.

## Running

No build step. Live at https://pablowilliams.github.io/VolcanoActivityTerminal/.

For local development, any static server works:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Data pipeline

The dashboard reads `data/quotes.json` on load and on each tick. A scheduled GitHub Action (`.github/workflows/refresh-data.yml`) regenerates synthetic close histories every hour so the visible data evolves. Replace the generator with a real data source to go live.

## Architecture

- `index.html` — semantic layout, landmarks, headings
- `app.js` — data, Monte Carlo engine, sentiment, signal logic, rendering
- `styles.css` — dark terminal theme with AA-contrast tokens

## License

Private. All rights reserved.
