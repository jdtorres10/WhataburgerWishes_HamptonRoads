# Whataburger Hampton Roads — Franchise Site Analysis

> An independent geospatial research project identifying optimal Whataburger franchise locations in the Hampton Roads, Virginia MSA — the largest untapped Whataburger market on the East Coast.

[![Live Map](https://img.shields.io/badge/Live%20Map-View%20Interactive-E2401C?style=for-the-badge)](https://yourusername.github.io/whataburger-hampton-roads)
[![License: MIT](https://img.shields.io/badge/License-MIT-F5F0E8?style=for-the-badge)](LICENSE)
[![Data: Public](https://img.shields.io/badge/Data-100%25%20Public-97C459?style=for-the-badge)](#data-sources)

---

## The Case for Hampton Roads

Hampton Roads is home to **1.79 million people**, **nine military installations**, and **83,000+ active duty service members** — with no Whataburger within 400 miles. The nearest location is in Charlotte, NC.

Texas contributes more enlisted personnel to the US military than any other state, and Hampton Roads is the largest Naval concentration on the East Coast. That means a disproportionate share of those 83,000 service members grew up eating Whataburger. This project asks: **where should the first location go?**

---

## What's in This Repository

| File | Description |
|------|-------------|
| `index.html` | Interactive Leaflet.js map — open in any browser |
| `whataburger_executive_onepager.pdf` | Pitch-ready one-page business summary |
| `whataburger_scoring_methodology.pdf` | 3-page methodology, site scores, and limitations |
| `whataburger_data_sources.pdf` | Full citation sheet for all public datasets used |
| `whataburger_github_publishing_guide.pdf` | How this project was published to GitHub Pages |

---

## The Interactive Map

**[→ Open the live map](https://yourusername.github.io/whataburger-hampton-roads)**

The map includes:

- **10 scored candidate sites** ranked by composite score (0–100)
- **9 military installation outlines** (Naval Station Norfolk, JBLE Langley AFB, Fort Eustis, NAS Oceana, and more)
- **Interstate and commercial corridor overlays** (I-64, I-664, Mercury Blvd, Jefferson Ave, Military Hwy)
- **Tabbed side panel** — browse candidate sites or military installations, click for detail cards
- **Filter controls** — isolate High / Medium / Lower priority sites or toggle military overlays

Click any map pin or installation polygon to open a detail card with demographics, scores, rationale, strengths, and considerations.

---

## Scoring Methodology

Each site was evaluated on four criteria derived entirely from public datasets:

| Criterion | Weight | Source |
|-----------|--------|--------|
| Population Density & Demographics | 30% | Census ACS 2024 (B01003, B19013) |
| Highway & Interchange Access | 30% | VDOT 2023 AADT Traffic Counts |
| Commercial Corridor Density | 25% | BLS QCEW (NAICS 722513), Census LODES |
| Military Installation Proximity | 15% | DoD DMDC, DoD Base Structure Report FY2023 |

Sub-scores normalized to 0–10 scale. Composite score = weighted sum × 10, rounded to nearest integer.

See [`whataburger_scoring_methodology.pdf`](whataburger_scoring_methodology.pdf) for the full breakdown including site-by-site scores and methodology limitations.

---

## Top Candidate Sites

| Rank | Site | Score | Priority |
|------|------|-------|----------|
| 1 | Mercury Blvd / I-64 — Hampton | 94 | 🟢 High |
| 2 | Jefferson Ave / I-64 — Newport News | 92 | 🟢 High |
| 3 | Military Hwy / I-64 — Norfolk | 91 | 🟢 High |
| 4 | Virginia Beach Blvd / I-264 — Virginia Beach | 90 | 🟢 High |
| 5 | Northampton Blvd / US-13 — Virginia Beach North | 82 | 🟡 Medium |
| 6 | Portsmouth Blvd / I-664 — Chesapeake | 79 | 🟡 Medium |
| 7 | Tidewater Dr / I-264 — Portsmouth | 77 | 🟡 Medium |
| 8 | **Victory Blvd — Hampton *(Your Site)*** | **74** | 🟡 Medium |
| 9 | Magruder Blvd / US-60 — Hampton NW | 68 | 🔴 Lower |
| 10 | Oceana Blvd / US-58 — Virginia Beach East | 65 | 🔴 Lower |

### Featured: Victory Blvd, Hampton (Site #8)

An existing freestanding drive-through building (former Pizza Hut) located **2.5 miles from JBLE Langley AFB Gate 20** on the Victory Blvd corridor. Key advantages:

- Existing drive-through infrastructure = significantly reduced buildout cost vs. greenfield
- VDOT actively widening Victory Blvd (rising long-term corridor value)
- Peninsula Town Center (70+ shops) and Boo Williams Sportsplex drive consistent traffic
- Direct Air Force family and civilian workforce corridor

---

## Why the Military Market Matters

| Installation | Branch | Personnel |
|---|---|---|
| Naval Station Norfolk | Navy | ~46,000 active + 21,000 civilian |
| JBLE — Langley AFB | Air Force | ~11,000 active duty |
| JBLE — Fort Eustis | Army | ~8,500 active duty |
| JEB Little Creek–Fort Story | Navy/Joint | ~17,000 active duty |
| NAS Oceana | Navy | ~10,000 active duty |
| Norfolk Naval Shipyard | Navy | ~4,000 mil + 9,000 civilian |
| NSA Hampton Roads | Navy | ~5,000 military & civilian |
| Naval Weapons Station Yorktown | Navy | ~1,500 military & civilian |
| USCG Sector Hampton Roads | Coast Guard | ~500 active duty |

**~12,000** of these personnel are estimated to be Texas-origin — a built-in brand-loyal customer base with zero current access to Whataburger in Virginia.

---

## Data Sources

All data used in this project is publicly available and free of charge:

- **U.S. Census Bureau** — ACS 5-Year Estimates 2024, LODES, TIGER/Line Shapefiles
- **VDOT** — 2023 Annual Average Daily Traffic (AADT) counts
- **Bureau of Labor Statistics** — QCEW (NAICS 722513), LAUS
- **Department of Defense** — DMDC installation data, Base Structure Report FY2023
- **Hampton Roads Alliance** — Military Economic Impact Report 2023
- **OpenStreetMap / CartoDB** — Base map tiles

See [`whataburger_data_sources.pdf`](whataburger_data_sources.pdf) for full citations and URLs.

---

## Running Locally

No build step required. Clone the repo and open `index.html` in any browser:

```bash
git clone https://github.com/yourusername/whataburger-hampton-roads.git
cd whataburger-hampton-roads
open index.html   # macOS
# or double-click index.html in File Explorer on Windows
```

An internet connection is required for the CartoDB map tiles and Leaflet.js CDN to load.

---

## Potential Next Steps

- [ ] Add drive-time isochrone layers (5 and 10-minute catchment areas) using Mapbox Isochrone API
- [ ] Pull live Census demographics via Python + Census API (`api.census.gov`)
- [ ] Add QSR competitor POI layer using Overture Maps Foundation open data
- [ ] Build a GeoPandas/Folium notebook that documents the full scoring pipeline
- [ ] Commission formal VDOT traffic study for Victory Blvd site

---

## Disclaimer

This is an independent research project and is not affiliated with, endorsed by, or submitted to Whataburger Restaurants LLC. All analysis is for educational and portfolio purposes only.

---

## License

MIT License — see [LICENSE](LICENSE) for details.  
Map code and methodology are open for reuse with attribution.  
*Site scoring data and written analysis represent original research work.*

---

*Prepared March 2026 · Hampton Roads, Virginia*
