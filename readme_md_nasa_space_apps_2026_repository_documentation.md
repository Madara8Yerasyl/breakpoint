# BREAKPOINT GeoSpatial Engine

**Multi-Decadal Earth System Change Analysis (1984–2026) and Evidence-Based Land Investigation Platform**

* **Competition:** NASA Space Apps Challenge 2026 — *Be An Earth System Trend Detective!*
* **Team:** **OY BAY** (Kanat Turemuratov, Yerassyl Makhsut, Yegor Shayakhmetov, Yeremey Klivtsov)
* **Study Region:** Astana and Akmola Region, Kazakhstan (Small Taldykol Basin, Astana Green Belt, Shortandy Steppe Plateau, Arshaly Steppe Control)
* **Live Interactive Demo (GitHub Pages):** Open `index.html` directly in any browser or via your enabled GitHub Pages URL.

---

## 1. Scientific Summary & Key Findings

**BREAKPOINT GeoSpatial Engine** integrates open multi-decadal Earth observation archives (1984–2026), climate reanalysis datasets, nonparametric trend statistics, and a 14-factor preliminary land-screening architecture (`MCDA-14`) with Expected Value of Sample Information (`EVSI`) borehole prioritization.

From the cryptographically verified Google Earth Engine export (`astana_nasa_1984_2026_verified.json`, 215 source-year blocks, 210 regional background calibration samples within a 50 km buffer):

| Study Zone | Variable | Valid Years ($n$) | Theil–Sen Slope / yr | 95% Confidence Interval | BH-FDR $q$-value | Interpretation |
| :--- | :--- | :---: | :---: | :---: | :---: | :--- |
| **Small Taldykol (`AST-ZONE-08`)** | **NDVI** | 39 | `-0.005701` | `[-0.007891, -0.003893]` | `0.01246` | Statistically significant vegetation loss |
| **Small Taldykol (`AST-ZONE-08`)** | **NDBI** | 39 | `+0.002935` | `[+0.001537, +0.004827]` | `0.00131` | Statistically significant urban/fill expansion |
| **Small Taldykol (`AST-ZONE-08`)** | **LST (°C)** | 39 | `+0.175361 °C` | `[+0.069312, +0.229361]` | `0.00154` | Statistically significant surface warming |
| **Astana Green Belt (`GREENBELT-09`)** | **NDVI** | 39 | `+0.008893` | `[+0.006778, +0.010407]` | `7.40e-8` | Statistically significant afforestation vigor |
| **Astana Green Belt (`GREENBELT-09`)** | **NDBI** | 39 | `-0.005827` | `[-0.007353, -0.003918]` | `1.84e-5` | Statistically significant built-up reduction |
| **Astana Green Belt (`GREENBELT-09`)** | **LST (°C)** | 39 | `-0.068815 °C` | `[-0.185172, +0.080761]` | `0.42296` | Non-significant absolute cooling ($q > 0.05$) |
| **Arshaly Steppe Control** | **LST (°C)** | 40 | `+0.124079 °C` | `[+0.006882, +0.308181]` | `0.07838` | Regional background reference |

* **Relative Thermal Divergence ($\Delta\beta_{\text{div}}$):** `+0.244176 °C/yr` (`+0.262495 °C/yr` paired annual difference, 95% CI `[+0.175518, +0.347175]`), confirmed via a Landsat 8-only sensitivity check (2013–2026: `+0.475319 °C/yr`).

---

## 2. Repository Structure

```text
breakpoint-geospatial-engine/
├── index.html                                        # Zero-dependency Interactive GIS & AI Site Copilot Web App
├── breakpoint_engine.py                              # Python Statistical & MCDA-14 / EVSI Computational Core
├── astana_nasa_1984_2026_verified.json               # Audited Google Earth Engine Export (1984–2026)
├── BREAKPOINT_OY_BAY_Scientific_Report_Updated.pdf   # Full 23-Page Scientific & Technical Report
└── README.md                                         # Project Documentation, Data Provenance & AI Disclosure
```

---

## 3. Quick Start for Judges

### Option A: Zero-Install Browser Execution (Recommended)
1. Open `index.html` directly in Chrome, Edge, Firefox, or Safari (or click the GitHub Pages deployment link).
2. Click **"Load GEE JSON"** in the top toolbar to upload `astana_nasa_1984_2026_verified.json` (or explore the pre-loaded audited Astana & Akmola regional telemetry).
3. Test the **AI Site Copilot** on the left panel using any preset or custom natural-language brief (e.g., *"Identify a flat 150+ ha plateau with high solar irradiance outside protected parks"* or *"Evaluate residential construction inside Drained Taldykol"*).
   * *Note on Long-Term Availability:* The Copilot uses a deterministic, zero-key browser NLP & `MCDA-14` engine with optional external LLM API hook—guaranteeing 100% uptime for judging without API rate limits or key expiration.

### Option B: Python Statistical Audit (`breakpoint_engine.py`)
```bash
pip install numpy scipy
python breakpoint_engine.py --data astana_nasa_1984_2026_verified.json
```

---

## 4. NASA & Partner Data Sources

* **USGS / NASA Landsat 5 TM, 7 ETM+, 8 OLI/TIRS, 9 OLI-2/TIRS-2 (Collection 2 Level-2):** 30 m surface reflectance and thermal LST (`1984–2026`).
* **NASA GPM IMERG Monthly V07:** Precipitation covariates (`~11 km`).
* **NASA JPL NASADEM & MERIT Hydro:** 30 m elevation/slope and 90 m Topographic Wetness Index (`TWI`).
* **NASA VIIRS VNP46A2:** Nighttime lights radiance (`~500 m`, `2012–2026`).
* **ESA Copernicus Sentinel-2 MSI Level-2A & ECMWF ERA5-Land:** 10/20 m optical boundary detail and seasonal air-temperature reanalysis.
* **EC JRC Global Surface Water v1.4:** Historical open-water occurrence (`1984–2021`).

---

## 5. Data & Artificial Intelligence (AI) Disclosure

NASA, USGS, ESA, ECMWF, and JRC datasets are external open-access archives; their inclusion does not imply agency endorsement of BREAKPOINT. Large Language Model (LLM) tools were used strictly as an engineering assistant for code structuring and English technical editing. All scientific hypotheses, Google Earth Engine pipelines, Theil–Sen / Hamed–Rao / BH-FDR calculations, SHA-256 verification (`d5810e8ed8c7445ac03a2de3d731f6df4c195ed3c160780288ce2abf2fe4335f`), and expert review with **LLP “OTN Engineering”** (Astana, Kazakhstan) were executed and verified by Team OY BAY.