# Brown Family Agency Reporting

Static GOAL reporting site for Brown Family Agency, deployed on Vercel from this repo. Pushes to `main` redeploy automatically.

| File | URL | Page |
| --- | --- | --- |
| `public/index.html` | `/` | Report hub |
| `public/reports/ga-campaign-overview-2026-10-14.html` | `/reports/ga-campaign-overview-2026-10-14` | Campaign overview, Sep 30 to Oct 14 |
| `public/reports/ga-home-campaign-performance-2026-10-14.html` | `/reports/ga-home-campaign-performance-2026-10-14` | GA Home performance, Sep 30 to Oct 14 |
| `public/reports/ga-auto-campaign-performance-2026-10-14.html` | `/reports/ga-auto-campaign-performance-2026-10-14` | GA Auto performance, Sep 30 to Oct 14 |
| `public/reports/ga-home-campaign-configuration-2026-09-29.html` | `/reports/ga-home-campaign-configuration-2026-09-29` | GA Home configuration |
| `public/reports/ga-auto-campaign-configuration-2026-09-29.html` | `/reports/ga-auto-campaign-configuration-2026-09-29` | GA Auto configuration |
| `public/reports/ga-home-value-targeting-research-2026-09-25.html` | `/reports/ga-home-value-targeting-research-2026-09-25` | GA Home value targeting research |
| `public/reports/ga-zip-expansion-map-2026-10-14.html` | `/reports/ga-zip-expansion-map-2026-10-14` | GA ZIP expansion map |
| `public/data/ga-zip-home-value-density-2026-09-25.csv` | `/data/ga-zip-home-value-density-2026-09-25.csv` | ZIP-level research data (download) |
| `public/data/ga-county-home-value-density-2026-09-25.csv` | `/data/ga-county-home-value-density-2026-09-25.csv` | County-level research data (download) |

Everything under `public/` is served. GOAL exports (campaign performance, source settings, RightPricing, call data) are git-ignored and must never be committed here. `vercel.json` pins the output directory to `public`, enables clean URLs, and sends `noindex` headers. There is no build step: Framework Preset **Other**, no build or install command.

## Design

Every page uses the GOAL Structured Dashboard (v2) design: Sora headings and numbers, Outfit text, and color tokens in CSS variables. Pages open in the viewer's system light or dark mode. The round toggle in the top-right corner overrides it and saves the choice under the `goal-theme` key, which all pages on the site share. Print is always light and hides the toggle. Colors in page bodies come from the tokens (`var(--brand)`, `var(--map-1)` and so on), never from hex values, so they switch with the theme.

Each page is self-contained: both GOAL wordmarks (black for light mode, white for dark) are inlined as base64. Maps are inline SVGs styled by the theme tokens: the county map in each configuration report, and the county and ZIP choropleths in the research report, where each area has a hover tooltip with its figures. Each report links back to the hub with the "All Reports" button in its sidebar and lists its related reports below the section nav.

Research data sources: ACS 2020-2024 5-year (B25075, B25077, B25003, B25036), Zillow ZHVI August 2026, Census 2020 ZCTA-county relationship file, Census cartographic boundary files.
