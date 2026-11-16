# Haze Watch

A single-page haze and weather monitor for Singapore and Southeast Asia.

- **Haze (Singapore only):** 24-hour PSI, PM2.5 and PM10 by region, from the National Environment Agency via [data.gov.sg](https://data.gov.sg) (`https://api-open.data.gov.sg/v2/real-time/api/psi`).
- **Weather (Singapore and 10 ASEAN cities):** from [Open-Meteo](https://open-meteo.com) (`https://api.open-meteo.com/v1/forecast`).

It is plain HTML, CSS and JavaScript. There is no build step and no dependencies. Data is fetched in the browser and refreshes every 10 minutes.

## Deploy to Vercel

1. Push this folder to a GitHub repository (`index.html` must be at the repo root).
2. In Vercel, choose **Add New → Project** and import the repository.
3. Set **Framework Preset** to **Other**. Leave Build Command and Output Directory empty.
4. Click **Deploy**.

To test locally, open `index.html` in a browser, or run `npx serve .` in this folder.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app |
| `vercel.json` | Clean URLs and basic security headers |
| `.gitignore` | Keeps local and Vercel metadata out of git |

## Data notes

- If the NEA feed can't be reached, the haze section shows a saved reading (marked as saved on the page) instead of live values. If Open-Meteo can't be reached, the weather cards show a retry button.
- data.gov.sg allows a limited number of calls per 10 seconds without an API key. One page load makes one call to each service, so normal use is well within the limit.
- Attribution: contains information from the Pollutant Standards Index (PSI) dataset accessed from data.gov.sg, made available under the terms of the Singapore Open Data Licence version 1.0. Weather data by Open-Meteo.com (free for non-commercial use; check their terms before commercial use).
