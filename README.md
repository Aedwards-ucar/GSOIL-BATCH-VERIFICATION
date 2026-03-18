# GSOIL-BATCH-VERIFICATION

Interactive visualization and analysis tools for ground soil heat flux sensor batch verification testing at NCAR's Earth Observing Laboratory, Callab.

**Live site:** [aedwards-ucar.github.io/GSOIL-BATCH-VERIFICATION](https://aedwards-ucar.github.io/GSOIL-BATCH-VERIFICATION/)

---

## Pages

| Page | File | Description |
|------|------|-------------|
| Landing | `index.html` | Project home — links to all test visualizations |
| Gsoil Heatmap | `gsoil_heatmap.html` | Interactive spatial heatmap for Calibration Runs 1 & 2 |
| Tsoil Analysis | `tsoil1.html` | Heat storage correction analysis (Calibration Run 2, preliminary) |

> Additional test pages will be added here as new calibration runs are completed.

---

## Repository Structure

```
GSOIL-BATCH-VERIFICATION/
│
├── index.html                  # Landing page
├── gsoil_heatmap.html          # Gsoil interactive heatmap (Runs 1 & 2)
├── tsoil1.html                 # Tsoil storage analysis (Run 2, preliminary)
│
├── ISFS_logo.png               # ISFS logo
├── NCAR_logo.png               # NSF NCAR logo
│
└── README.md                   # This file
```

---

## Calibration Tests

### Run 1 — March 6, 2026
- **Sensors:** 28 Gsoil plates (GS112–GS159, HF138) on motes M2–M7
- **Sandbox:** 15 × 24 in
- **Event window:** 16:00–23:00 UTC
- **Peak flux:** ~97 W/m² (GS123)
- **Visualization:** Tab 1 in `gsoil_heatmap.html`
- **Notes:** March 5 data excluded (anomalous spike ~286 W/m²)

### Run 2 — March 12, 2026
- **Sensors:** 16 Gsoil plates + 4 Tsoil probe arrays (probes 036, 139, 141, 149)
- **Sandbox:** 15 × 24 in
- **Event window:** 16:30 UTC Mar 12 – 03:00 UTC Mar 13
- **Peak flux (plates):** ~38 W/m² (GS154); estimated surface flux G(0) ~53 W/m²
- **Visualization:** Tab 2 in `gsoil_heatmap.html`; storage analysis in `tsoil1.html`
- **Notes:** Preliminary test — Cv assumed (dry sand), Tsoil probes not co-located with plates. See warnings in `tsoil1.html`.

---
<!-- ADD NEW TESTS BELOW THIS LINE -->

### Run 3 — *(Planned)*
- **Sensors:** TBD
- **Improvements planned:** Measured soil thermal properties (TP01), co-located Tsoil/Gsoil pairs, longer cool-down window
- **Visualization:** TBD

---

## Sensors

### Gsoil Plates (Run 1 — 28 sensors)

| Sensor | Key | Mote | Sensor | Key | Mote |
|--------|-----|------|--------|-----|------|
| GS112 | a2 | M2 | GS135 | a5 | M5 |
| GS114 | b2 | M2 | GS137 | b5 | M5 |
| GS115 | c2 | M2 | HF138 | c5 | M5 |
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

> HF138 is a heat flux plate sensor; all others are ground soil (GS) sensors.

### Gsoil Plates (Run 2 — 16 sensors)

| Sensor | Key | Mote | Sensor | Key | Mote |
|--------|-----|------|--------|-----|------|
| GS112 | a2 | M2 | GS142 | a6 | M6 |
| GS114 | b2 | M2 | GS150 | b6 | M6 |
| GS115 | c2 | M2 | GS151 | c6 | M6 |
| GS117 | d2 | M2 | GS152 | d6 | M6 |
| GS118 | e2 | M2 | GS153 | e6 | M6 |
| GS119 | a3 | M3 | GS154 | a7 | M7 |
| GS120 | b3 | M3 | | | |
| GS121 | c3 | M3 | | | |
| GS122 | d3 | M3 | | | |
| GS123 | e3 | M3 | | | |

### Tsoil Probes (Run 2 — 4 probe arrays)

Each probe array contains 4 thermistors at depths 0.6, 1.9, 3.1, and 4.4 cm. Probes are positioned in the gaps between the four Gsoil sensor clusters, oriented facing the center, spanning from the Gsoil plate depth (~5 cm) up to the sand surface.

| Probe ID | Ports | Location |
|----------|-------|----------|
| 036 | b7 | Between clusters (NW gap) |
| 139 | c7 | Between clusters (NE gap) |
| 141 | d7 | Between clusters (SE gap) |
| 149 | e7 | Between clusters (SW gap) |

---

## Methods

### Heatmap Interpolation
Heat flux values between sensor points are interpolated using a radial basis function (RBF) with Gaussian kernel (σ = 3.5 × scale). Boundary anchor points are placed around the sandbox perimeter at 40% of the minimum sensor value per frame, pulling edge values down to near-ambient. All rendering is done client-side on an HTML5 canvas with DPR scaling.

### Heat Storage Correction (Tsoil Analysis)
Surface heat flux G(0) is estimated using the combination method (Fuchs & Tanner, 1968):

```
G(0) = G(zp) + ΔS
ΔS   = Cv · (ΔT̄/Δt) · zp
```

Where G(zp) is the Gsoil plate reading at depth zp = 5 cm, T̄ is the mean of the 4 Tsoil temperatures, Δt = 600 s (10-min interval), and Cv = 1.2 MJ m⁻³ K⁻¹ (assumed, dry sand). See `tsoil1.html` for full methodology, caveats, and references.

---

## Data Pipeline

Raw data is exported from the NCAR ISFS DSM using the `prep` (Nidas) command:

```bash
# Example: Extract Run 2 sensors
/opt/nidas/bin/prep -D Gsoil.a.2,Gsoil.b.2,...,Gsoil.a.7 \
  /net/isf/isfs/projects/callab/raw_data/30_GSOIL/16gsoils/30_GSOIL_20260312_120000.dat \
  /net/isf/isfs/projects/callab/raw_data/30_GSOIL/16gsoils/30_GSOIL_20260313_000000.dat \
  > gsoils2.txt
```

Data is then resampled to 10-minute averages via Python (pandas) and embedded as JSON in the HTML files.

---

## Known Issues & Notes

- **March 5 data excluded (Run 1)** — Anomalous spike (~286 W/m²) recorded; removed pending investigation
- **HF138 (c5, Run 1)** — Heat flux plate sensor; behavior may differ from GS units
- **Reversed wire polarity** — Some older GS units had factory-swapped red/black wires. Corrected on new connector installations
- **Cold solder joints** — Intermittent readings on some GS units resolved by reflowing analog input pins 0–8
- **Run 2 Cv assumed** — Volumetric heat capacity not measured
- **Tsoil/Gsoil spatial mismatch** — Probes positioned between clusters, not co-located with individual plates

---

## Background

As part of batch verification, sensors are placed in a sandbox and exposed to a controlled heat lamp event. Readings are logged via the NCAR ISFS data system and reviewed to confirm:

- Sensors respond correctly relative to the white dot polarity marker
- COF values in the Wizard produce expected W/m² output
- No intermittent connections or anomalous readings are present before field deployment
- Sensor spatial distribution and response characteristics match expectations

---

## References

1. Fuchs, M. & Tanner, C.B. (1968). Calibration and field test of soil heat flux plates. *Soil Sci. Soc. Am. Proc.*, 32, 326–328.
2. Cobos, D.R. & Baker, J.M. (2003). In situ measurement of soil heat flux with the gradient method. *Vadose Zone Journal*, 2, 589–594.
3. Ochsner, T.E., Sauer, T.J. & Horton, R. (2007). Soil heat storage measurements in energy balance studies. *Agronomy Journal*, 99, 311–319.
4. Sauer, T.J., Horton, R. & Logsdon, S.D. (2003). Soil heat flux plate performance in laboratory and field conditions. *SSSAJ*, 67, 627–634.
5. Gao, Z. et al. (2017). A novel approach to evaluate soil heat flux calculation. *JGR Atmospheres*, 122, 6934–6949.

---

Anthony Edwards — aedwards@ucar.edu  
Earth Observing Laboratory, NSF National Center for Atmospheric Research (NCAR)
