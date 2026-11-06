# Prop 3 vs. the Bike Network

By Jack Satriano · [@satriano.io](https://bsky.app/profile/satriano.io) on Bluesky

A static site comparing support for NYC's Nov 3, 2026 Proposal 3 (street safety charter amendment) in every election district with nearby protected bike infrastructure and car ownership, to show where support outruns the infrastructure. Layers: support gap, opportunity (support gap × car-free share × square-rooted density), Yes share, bike infrastructure, car ownership and density.

> This page was built with Claude, an AI model made by Anthropic. The data processing, analysis and code were AI-generated under human direction. Check figures against the listed sources before citing.

Everything is in `public/index.html` (data inlined, no build step).

## Deploy to Vercel

**Option A — CLI** (needs Node.js):

```
cd prop3-bike-map
npx vercel          # first run links/creates the project; answer the prompts
npx vercel --prod   # production deploy
```

**Option B — Git:** push this folder to a GitHub repo, then on vercel.com choose *Add New → Project*, import the repo and deploy. No framework or build settings are needed; `vercel.json` points Vercel at `public/`.

## Preview locally

```
npx serve public
```

## Sources and acknowledgements

- Results: NYC Board of Elections unofficial election night results, as of Nov 4, 2026, 12:42 AM (https://web.enrboenyc.us/CD27771ADI0.html). These will change as remaining ballots are counted.
- Election district shapes: NYC Planning release 25C. 8 districts redrawn for 2026 (3,064 votes) have no shape.
- Bike routes: NYC DOT, New York City Bike Routes (NYC Open Data), current segments only. Scoring method is documented on the page.
- Car ownership: U.S. Census Bureau ACS 2017–2021 5-year estimates (vehicles available), via NYC DCP Population FactFinder (https://github.com/NYCPlanning/db-factfinder).
- Population density: ACS 2017–2021 total population, same DCP FactFinder extract.
- Census tract boundaries: NYC DCP 2010 Census Tracts (20A) via https://github.com/nycehs/NYC_geography.
- Inspiration: CUNY Center for Urban Research, NYC 2026 election map (https://www.urbanresearchmaps.org/electioncompare2026/).
- Election district boundaries copy via https://github.com/ry-li/map-nyc-election.
- Tools: Python (shapely, pyproj, pyshp, openpyxl). Analysis and map built with the help of Claude (Anthropic).
