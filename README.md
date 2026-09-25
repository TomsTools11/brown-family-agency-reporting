# Brown Family Agency Reporting

Static GOAL reporting site for Brown Family Agency, deployed on Vercel from this repo. Pushes to `main` redeploy automatically.

| File | URL | Page |
| --- | --- | --- |
| `public/index.html` | `/` | Report hub |
| `public/reports/ga-home-campaign-configuration-2026-09-25.html` | `/reports/ga-home-campaign-configuration-2026-09-25` | GA Home configuration |
| `public/reports/ga-auto-campaign-configuration-2026-09-25.html` | `/reports/ga-auto-campaign-configuration-2026-09-25` | GA Auto configuration |

Everything under `public/` is served. `vercel.json` pins the output directory to `public`, enables clean URLs, and sends `noindex` headers. There is no build step: Framework Preset **Other**, no build or install command.

County maps live in `public/assets/` and load as `<img>` from the reports. Each report links back to the hub with the "All Reports" button in its sidebar.
