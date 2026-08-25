# 🌾 Crop Production Dashboard

Interactive analytics for India's crop harvest data — built as a self-contained HTML dashboard and a companion Power BI report. Explore yield, rainfall, and area sown across 11 states and 6 crops from the 2023 and 2024 growing seasons.

<p align="left">
  <img alt="records" src="https://img.shields.io/badge/records-502-B4860B">
  <img alt="states" src="https://img.shields.io/badge/states-11-445E39">
  <img alt="crops" src="https://img.shields.io/badge/crops-6-2F4374">
  <img alt="years" src="https://img.shields.io/badge/seasons-2023--2024-8C4A2F">
  <img alt="license" src="https://img.shields.io/badge/license-MIT-lightgrey">
</p>

## Overview

`CropProduction.xlsx` holds harvest-level records — one row per field entry, logged by state and crop, with area sown, tonnes yielded, and rainfall received. This repo turns that raw ledger into two things:

- **`CropProduction_Dashboard.html`** — a single-file, no-build interactive dashboard (vanilla JS + Chart.js) that runs entirely in the browser
- **`CropProDashboard.pbix`** — the same dataset modeled as a Power BI report for users who prefer Microsoft's BI tooling

## Features

- **Live filters** — isolate one or more crops, a single state, or a growing year, and every chart and table updates instantly
- **Yield & rainfall analysis** — total yield by crop, average yield per hectare by state, and a rainfall-vs-yield scatter plot to spot correlation
- **Seasonal trends** — monthly harvest volume compared across 2023 and 2024
- **Harvest calendar** — a tally-style heat strip showing which months each crop is typically brought in
- **Searchable, sortable ledger** — the full 502-row dataset, paginated and sortable by any column
- **Zero dependencies to run** — open the HTML file directly; no server, build step, or install required

## Data schema

| Column         | Type   | Description                              |
|----------------|--------|-------------------------------------------|
| `RecordID`     | string | Unique identifier for the harvest entry   |
| `State`        | string | Indian state where the crop was grown     |
| `CropName`     | string | Wheat, Rice, Maize, Cotton, Sugarcane, or Pulses |
| `HarvestDate`  | date   | Date the crop was harvested               |
| `AreaHectares` | number | Area sown, in hectares                    |
| `YieldTonnes`  | number | Total yield, in tonnes                    |
| `RainfallMM`   | number | Rainfall received during the growing period, in millimetres |

## Getting started

### View the HTML dashboard

No installation needed — just open it in a browser.

```bash
git clone https://github.com/<your-username>/crop-production-dashboard.git
cd crop-production-dashboard
open CropProduction_Dashboard.html   # macOS
# or: start CropProduction_Dashboard.html   (Windows)
# or: xdg-open CropProduction_Dashboard.html (Linux)
```

The dataset is embedded directly in the file, so it also works offline and can be shared as a single attachment.

### Open the Power BI report

1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (Windows only).
2. Open `CropProDashboard.pbix`.
3. If prompted, point the data source to your local copy of `CropProduction.xlsx`.

## Project structure

```
.
├── CropProduction.xlsx           # Source dataset
├── CropProduction_Dashboard.html # Standalone interactive dashboard
├── CropProDashboard.pbix         # Power BI report
└── README.md
```

## Tech stack

- **[Chart.js](https://www.chartjs.org/)** for charts (bar, scatter, line)
- **Vanilla JavaScript** for filtering, sorting, and search — no framework or build step
- **Power BI** for the desktop-report alternative

## Live Demo: 
**Here**: https://harvest-map-zeta.vercel.app/

## Roadmap

- [ ] Add district-level granularity
- [ ] Include cost-of-cultivation and profitability metrics
- [ ] Publish a hosted version of the HTML dashboard via GitHub Pages

## Contributing

Issues and pull requests are welcome. For larger changes, please open an issue first to discuss what you'd like to change.

## License

[MIT](LICENSE)
