# CPI Inflation Monitor

**Designed and Developed by Emmanuel Kuh**

CPI Inflation Monitor is a single-file economic analytics dashboard that turns Consumer Price Index data into a clear view of inflation pressure, category changes, inflation cost differences, and plain-English interpretation.

The project is built for a portfolio because it shows data retrieval, time-series transformation, inflation calculations, custom visualization, responsive interface design, and browser-based voice briefing in one polished experience.

## What It Does

- Loads CPI-U data from the U.S. Bureau of Labor Statistics Public Data API when the browser request succeeds
- Tracks headline CPI, core CPI, food, energy, shelter, medical care, transportation, apparel, and education and communication
- Calculates not seasonally adjusted year-over-year inflation
- Uses seasonally adjusted CPI series for month-to-month movement where BLS publishes an adjusted series
- Shows a premium inflation heatmap for quick category comparison
- Includes a custom canvas chart without requiring Chart.js
- Provides an experimental CPI Pressure Index based on inflation speed, category breadth, and volatility
- Explains the latest reading in natural language
- Speaks the inflation briefing with the browser's built-in voice system
- Includes an inflation cost illustration for a selected category basket
- Works on desktop, tablet, and phone screens
- Displays a prominent Demo Mode banner with simulated values if a browser blocks the BLS request

## Data Source

The dashboard uses the BLS Public Data API:

https://www.bls.gov/developers/api_signature_v2.htm

Series IDs were checked against the BLS CPI series file:

https://download.bls.gov/pub/time.series/cu/cu.series

BLS seasonal-adjustment guidance was used to separate not seasonally adjusted year-over-year rates from seasonally adjusted month-to-month movement:

https://www.bls.gov/cpi/seasonal-adjustment/using-seasonally-adjusted-data.htm

Main not seasonally adjusted CPI series used for year-over-year inflation and index levels:

- `CUUR0000SA0` Headline CPI-U, all items, U.S. city average
- `CUUR0000SA0L1E` Core CPI, all items less food and energy
- `CUUR0000SAF1` Food
- `CUUR0000SA0E` Energy
- `CUUR0000SAH1` Shelter
- `CUUR0000SAM` Medical care
- `CUUR0000SAT` Transportation
- `CUUR0000SAA` Apparel
- `CUUR0000SAE` Education and communication

Seasonally adjusted versions of the same category series are requested with `CUSR` prefixes for month-to-month movement. The dashboard requests 18 total series across roughly eight calendar years, which stays below the public BLS limits documented for the API.

## How To Use

Open `cpi-inflation-dashboard.html` in a browser, or upload the included `index.html` version to a GitHub Pages repository.

For GitHub Pages:

1. Create a new repository.
2. Rename `cpi-inflation-dashboard.html` to `index.html`.
3. Upload the file.
4. Go to repository settings and enable GitHub Pages from the main branch.

## Notes

Demo Mode values are simulated for interface demonstration and should not be interpreted as actual CPI observations.

The CPI Pressure Index is an experimental dashboard-specific indicator, not an official BLS measure. It is designed to make the interface easier to read while keeping the methodology transparent.

This project is for research, education, and portfolio presentation. It is not policy, investment, or financial advice.
