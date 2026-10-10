# Off-Grid Solar Sizer

A single-page calculator that shows which PV and battery combinations run a home fully off-grid, for summer, monsoon and winter. It is one static file, `index.html`, with no build step and no server.

## What it does
- Takes the load for each of the 24 hours (select a range of hours, enter watts, apply).
- Runs a 24-hour day for each season: PV feeds the load first, the surplus charges the battery, the battery carries the night. The daily cycle repeats until the battery state settles.
- Shows off-grid or the kWh/day shortfall for all three seasons, the battery needed at the chosen PV size and the PV needed at the chosen battery size, and a chart of the minimum battery for every PV size.
- Heavy cloud and fog days are not modelled.

## Default assumptions (editable in the page)
| Item | Default |
|---|---|
| Sun hours, kWh per kWp per day | Summer 6.1, monsoon 4.9, winter 5.5 |
| System efficiency | 78% |
| Usable battery | 90% (reserve floor 10%) |
| Round-trip efficiency | 92% |

The sun hours are for Ludhiana, Punjab: PVGIS yield for a south-facing 25 degree array, averaged over summer (Apr to Jun), monsoon (Jul to Sep) and winter (Nov to Feb), divided by the 78% system efficiency. Battery % in the page is a percentage of the full nominal pack.

Settings are saved in the browser's local storage on the device.

## Run it
Open `index.html` in a browser. Styling uses Tailwind CSS from its CDN script (light theme, with the slanted-line gutters from tailwindcss.com), so the page needs an internet connection to look right.

## Publish on GitHub Pages
In the repository settings, set Pages to deploy from the `main` branch, root folder. The page is then served at `https://<user>.github.io/offgrid-solar-sizer/`.
