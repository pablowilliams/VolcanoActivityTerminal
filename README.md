# Eruption Watch

A scenario monitor for exploring how simplified seismic, thermal and deformation indicators alter a volcanic-activity watchlist.

## What it demonstrates

- Fixed-seed scenario generation with explicit horizon and path controls.
- A volcano comparison table with activity indicators and watch states.
- VEI and thermal-anomaly sensitivity views.
- Keyboard navigation, readable status text and chart alternatives.

All observations and forecasts are synthetic. This is not an operational warning product; official observatory and civil-protection guidance always takes precedence.

## Run locally

```bash
python3 -m http.server 8000
```

Open `http://localhost:8000`. The published version is available through GitHub Pages.

## Engineering note

The scenario kernel is shared with four sibling studies. Eruption Watch supplies its own volcanic-activity adapter, safety language and domain-specific panels.
