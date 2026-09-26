# Brown Family Agency Reporting

Static GOAL reporting site for Brown Family Agency, deployed on Vercel from this repo. Pushes to `main` redeploy automatically.

| File | URL | Page |
| --- | --- | --- |
| `public/index.html` | `/` | Report hub |
| `public/reports/ga-home-campaign-configuration-2026-09-25.html` | `/reports/ga-home-campaign-configuration-2026-09-25` | GA Home configuration |
| `public/reports/ga-auto-campaign-configuration-2026-09-25.html` | `/reports/ga-auto-campaign-configuration-2026-09-25` | GA Auto configuration |
| `public/reports/ga-home-value-targeting-research-2026-09-25.html` | `/reports/ga-home-value-targeting-research-2026-09-25` | GA Home value targeting research |
| `public/data/ga-zip-home-value-density-2026-09-25.csv` | `/data/ga-zip-home-value-density-2026-09-25.csv` | ZIP-level research data (download) |
| `public/data/ga-county-home-value-density-2026-09-25.csv` | `/data/ga-county-home-value-density-2026-09-25.csv` | County-level research data (download) |

Everything under `public/` is served. `vercel.json` pins the output directory to `public`, enables clean URLs, and sends `noindex` headers. There is no build step: Framework Preset **Other**, no build or install command.

County maps for the configuration reports live in `public/assets/` and load as `<img>`. The research report inlines its two choropleth SVGs (county and ZIP) so each area carries a hover tooltip with its figures. Each report links back to the hub with the "All Reports" button in its sidebar.

Research data sources: ACS 2020-2024 5-year (B25075, B25077, B25003, B25036), Zillow ZHVI August 2026, Census 2020 ZCTA-county relationship file, Census cartographic boundary files.
