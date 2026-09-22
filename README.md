# Elam View Plot

An interactive 3D model of a surveyed hillside plot at Thankamony, Idukki, Kerala (~9.8515° N, 77.0278° E, ~910 m ASL).

**Live page:** https://ashtvm13-pixel.github.io/elam-view-plot/

## What it shows

- The surveyed boundary — six lines totalling 207.8 m, enclosing 2442.36 m² (60.35 cents)
- The plot draped on real SRTM 30 m terrain, contoured at 5 m
- A 360° skyline traced from the house position out to 15 km
- A first-person view from inside the plot

## How the geometry was derived

The surveyor's sheet records six side lengths and one total area. That is seven numbers, while a
hexagon has eight shape degrees of freedom — so **the sheet alone does not determine the plot's
shape**, and it carries no bearings or corner coordinates.

The remaining degree of freedom is resolved from the ground: three of the six lines are road
frontage, so the F–G–H–C chain is seated on the road as it appears in satellite imagery, with
corner H on the inside of the road bend. The resulting polygon reproduces all six lengths to the
centimetre and returns 2442.36 m² exactly.

| Line | Adjoins | Length |
|------|---------|--------|
| A–B | Property of Bineesh | 52.8 m |
| B–C | Tiji Ummedathe | 51.7 m |
| C–H | road frontage | 21.9 m |
| H–G | road frontage | 31.9 m |
| G–F | road frontage | 28.8 m |
| F–A | Para (rock) | 20.7 m |

Plus a separate road strip of 93.26 m² (2.30 cents), tabulated but not drawn — the sheet gives its
dimensions without a position. Full total: 2535.62 m², 62.65 cents.

## Accuracy

- **Exact** — the six lengths and the area, taken from the survey sheet.
- **Approximate** — absolute position, anchored to a map pin at 9.852065, 77.02738 with a screenshot
  scale of ~0.136 m/px. The figure may sit some metres off true.
- **Interpolated** — ground height is SRTM 30 m. Right for the hillside trend, not a levelled survey.
  The 360° skyline is bare-earth terrain only; standing vegetation is not in the data and will close
  much of it down on the ground.

Not a legal document. For anything binding, or for cut-and-fill, use the surveyor's bearings or
corner coordinates.

## Running locally

Single self-contained file; three.js loads from a CDN.

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000
