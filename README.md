# GSOIL-BATCH-VERIFICATION

Interactive heatmap visualization for ground soil heat flux sensor batch verification testing at NCAR's Earth Observing Laboratory.

**Live site:** [aedwards-ucar.github.io/GSOIL-BATCH-VERIFICATION/gsoil_heatmap.html](https://aedwards-ucar.github.io/GSOIL-BATCH-VERIFICATION/gsoil_heatmap.html)

---

## Overview

This tool visualizes heat flux readings (W/m²) from 28 ground soil sensors (GS series) arranged across a 15 × 24 inch sandbox. Sensors are mounted on 6 wireless motes (M2–M7), each carrying up to 5 channels (a–e). The visualization is used to verify sensor calibration, identify bad solder joints or wiring issues, and compare sensor behavior across the sandbox during controlled heat lamp events.

---

## Sensors

| Sensor ID | Key | Mote | Sensor ID | Key | Mote |
|-----------|-----|------|-----------|-----|------|
| GS112 | a2 | M2 | GS135 | a5 | M5 |
| GS114 | b2 | M2 | GS137 | b5 | M5 |
| GS115 | c2 | M2 | GS138 | c5 | M5 |
| GS117 | d2 | M2 | GS140 | d5 | M5 |
| GS118 | e2 | M2 | GS141 | e5 | M5 |
| GS119 | a3 | M3 | GS142 | a6 | M6 |
| GS120 | b3 | M3 | GS150 | b6 | M6 |
| GS121 | c3 | M3 | GS151 | c6 | M6 |
| GS122 | d3 | M3 | GS152 | d6 | M6 |
| GS123 | e3 | M3 | GS153 | e6 | M6 |
| GS124 | a4 | M4 | GS154 | a7 | M7 |
| GS127 | b4 | M4 | GS157 | b7 | M7 |
| GS128 | c4 | M4 | GS159 | c7 | M7 |
| GS131 | d4 | M4 | | | |
| GS133 | e4 | M4 | | | |

---

## Data

- **Source:** NCAR ISFS DSM, exported via Nidas as timestamped ASCII (`gsoils.txt`)
- **Date range used:** March 6–10, 2026 (March 5 data excluded — identified as bad dataset)
- **Sample rate:** ~5 seconds raw; resampled to 10-minute averages for the timeline view
- **Units:** W/m²
- **Color scale:** Fixed at −10 to 100 W/m²

### Views
| View | Description |
|------|-------------|
| **Mar 6 Peak** | Maximum value per sensor during the Mar 6 heat lamp event (16:00–23:00) |
| **Baseline** | Mean sensor values during coverd conditions (Mar 7, 10:00–18:00) |
| **Timeline** | 10-minute averaged readings scrubbed across Mar 6 16:00–22:50 |

---

## Heatmap Features

- **Interpolated background** — Radial basis function (RBF) interpolation fills in heat distribution between sensor points
- **Sensor dots** — Colored by intensity to match the heatmap scale; labeled with GS/HF ID
- **Mote ring** — Subtle outer ring in mote color for grouping reference
- **Mote filter** — Buttons to isolate individual motes (M2–M7)
- **Hover tooltip** — Shows sensor ID, mote, W/m² value, and sandbox coordinates

---

## Charts

Three charts are rendered below the heatmap:

1. **Time Series** — All 28 sensors plotted over the Mar 6 window. Lines colored by mote. Hover to see the hottest sensor at any point in time.
2. **Mote Comparison** — Per-mote average W/m² over time. Useful for identifying which motes responded strongest to the heat source.
3. **Cool-down Curve** — Each sensor normalized to its own peak (100%), showing relative decay rate after peak. Sensors that cool faster may indicate different soil contact or sensor placement.

---

## Known Issues & Notes

- **March 5 data excluded** — An anomalous spike (~286 W/m²) was recorded on March 5 and has been removed from all views (touching with hands during setup testing) 
- **Negative COF sensors** — Some older Ground Soil units had red/black wires crossed at the factory. These have been corrected on new connector installations and should no longer require negative coefficients in the Wizard

---

## Background

As part of batch verification, sensors are placed in a sandbox and exposed to a controlled heat lamp event. Readings are logged via the NCAR ISFS data system and reviewed to confirm:
- Sensors respond correctly relative to the white dot polarity marker
- COF (coefficient) values in the Wizard produce expected W/m² output
- No intermittent connections or anomalous readings are present before field deployment

---

## Notes

GS128 (c4) has old board or failing ADC, wirde data -- 03/10/26

---
