---
name: country-climate-card
description: Make a one-page climate card for any country from three open datasets, with every number computed in code. Use when someone preparing a bilateral meeting, a briefing or a funding proposal gives a country name and wants its capital's heat trend, its emissions and biggest source, and its latest NDC on one page.
---

# Country climate card

One input: a country name. One output: a card a delegation adviser can read in ten seconds before a bilateral.
Every number comes from an API response you saved. Nothing comes from memory.

## 1. Pull the data (save each response to a file before you read it)

Use the ISO3 code (Kenya = `KEN`) and the capital's latitude and longitude to two decimals.

| What | URL |
|---|---|
| Daily max temperature, capital | `https://archive-api.open-meteo.com/v1/archive?latitude=<lat>&longitude=<lon>&start_date=1961-01-01&end_date=2025-12-31&daily=temperature_2m_max&timezone=auto` |
| Total emissions, one call per year 2015 to 2024 | `https://api.climatetrace.org/v6/country/emissions?countries=<ISO3>&since=<year>&to=<year>` |
| Emissions by sector, 2024, one call per sector | same URL with `&since=2024&to=2024&sectors=<sector>` for `agriculture buildings fluorinated-gases forestry-and-land-use fossil-fuel-operations manufacturing mineral-extraction power transportation waste` |
| NDC content | `https://www.climatewatchdata.org/api/v1/data/ndc_content?countries[]=<ISO3>&per_page=500` |

Climate TRACE: read `[0].emissions.co2e_100yr` (tonnes). `since` and `to` must be the same year, or you get a sum of years.
Open-Meteo is CC BY 4.0: credit it on the card.

## 2. Compute in code (Python, standard library is enough)

- **Hot-day line** `T` = the 90th percentile of all daily maxima 1961–1990, rounded to a whole degree.
- **Hot days per year** = days with max ≥ `T`. `base` = mean 1961–1990, `recent` = mean 2016–2025, `ratio` = recent / base.
- **Emissions**: total 2024 and change since 2015, in Mt CO₂e.
- **Sector shares**: drop `forestry-and-land-use` (it is often a net sink and swamps the rest), then each sector's share of the sum of the others. `top` = largest.
- **NDC**: for `ghg_target`, `conditionality` and `submission`, take the row with the highest `id` (the latest submission).
- **The sentence** (same rule for every country):
  - power share < 10% and top is not power → «Power is not its problem. Its <top> are.» (a small power share is not a clean grid, so never write «clean»)
  - otherwise → «Its <top> lead, at <share>%. <Second> come next, at <share>%.»
  - nouns: agriculture farms, transportation roads, manufacturing factories, buildings buildings, waste landfills, fossil-fuel-operations oil and gas fields, mineral-extraction mines, fluorinated-gases cooling gases.

## 3. Lay out the card (4:5, 1080 × 1350)

Top to bottom: the prompt line · country name · **hero `<ratio>×` more hot days in <capital>** with base and recent under it ·
bar chart of hot days per year 1961–2025, 2016–2025 in a warm colour, flat lines at base and recent · the sentence, second line bold ·
three tiles (emissions 2024 · biggest source · latest NDC) · one source line.
Phone rule: nothing a reader must read under 24 px.

## City mode («heat card for <city>»)

Open-Meteo only, with `daily=temperature_2m_max,temperature_2m_min` at the city's coordinates. Same hot-day line `T`.
Hero = `recent − base` more hot days a year. Add warm nights: nights with minimum above 20 °C, 1961–90 mean against 2016–25 mean.
Tiles: the hot-day line `T`, the worst year (most hot days), the hottest day in the series.

## 4. Hand back

The card, then a JSON block with `T base recent ratio total24 growth top share_top power_share ndc_submission conditionality sentence`,
then the raw `ghg_target` sentence word for word.

## What a person still checks

- The NDC line against the country's own NDC document on unfccc.int. Climate Watch is a reading of it.
- The grid cell: ERA5 is about 25 km. A coastal capital can land on sea.
- Emissions are Climate TRACE estimates, not the national inventory. Say so if the card goes into an official brief.
