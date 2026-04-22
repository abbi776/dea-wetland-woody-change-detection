# DEA Wetland Woody Change Detection

Open-source workflow for detecting, screening, and validating woody vegetation change across floodplain wetlands using **Digital Earth Australia Land Cover, Water Observations, Landsat Surface Reflectance NBART, Wetlands Insight Tool outputs, ANAE wetland boundaries, and river gauge data for hydrological interpretation**.

This repository contains all notebooks, environment requirements, and instructions needed to reproduce the analysis — from woody transition detection and screening to figure generation and case-study wetland interpretation.

---

## 🌱 Key Features
- Detection of woody vegetation encroachment and retreat from **DEA Land Cover**.
- Temporal stability screening of mapped transitions.
- Persistent-water masking using **DEA Water Observations (WOfS)**.
- Spectral plausibility assessment using **Landsat-derived EVI**.
- Wetland case-study assessment using the **Wetlands Insight Tool (WIT)**.
- Hydrological interpretation supported by **river gauge water-level plots**.
- Generation of publication-ready figures for:
  - encroachment and retreat trends
  - river gauge time series
  - EVI hexbin comparison plots

---

## 📂 Repository Structure

```text
dea-wetland-woody-change-detection/
│
├── scripts/
│   ├── 01_detect_woody_change_from_dea_land_cover.ipynb
│   ├── 02_temporal_stability_mask.ipynb
│   ├── 03a_persistent_water_mask_all_wetlands.ipynb
│   ├── 03b_persistent_water_mask_case_studies.ipynb
│   ├── 04_evi_plausibility.ipynb
│   ├── 05_wetlands_insight_tool_case_study.ipynb
│   ├── 06_plot_encroachment_retreat_trends.ipynb
│   ├── 07_plot_river_gauge_water_level.ipynb
│   └── 08_plot_evi_hexbin.ipynb
│
├── requirements.txt
├── LICENSE
├── .gitignore
└── README.md

```
---

## ⚙️ Installation
```bash
git clone https://github.com/abbi776/dea-wetland-woody-change-detection.git
cd dea-wetland-woody-change-detection

# Create a fresh environment (recommended)
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows

# Install required packages
pip install -r requirements.txt
```
---

## 🚀 Pipeline Steps

The workflow is organised into **numbered notebooks** for clarity:

1️⃣ **Detect woody change from DEA Land Cover**
```text
scripts/01_detect_woody_change_from_dea_land_cover.ipynb
```
Identifies woody encroachment and retreat across wetlands using fixed 5-year intervals and custom hydrological epochs.

2️⃣ **Apply temporal stability mask**
```text
scripts/02_temporal_stability_mask.ipynb
```
Screens transitions using majority-vote stability around baseline and target years.

3️⃣ **Apply persistent-water mask using DEA Water Observations**

All wetlands:
```text
scripts/03a_persistent_water_mask_all_wetlands.ipynb
```
Case-study wetlands:
```text
scripts/03b_persistent_water_mask_case_study.ipynb
```
Removes transitions associated with persistently inundated areas and quantifies encroachment and retreat before and after masking.

4️⃣ **Assess EVI plausibility**
```text
scripts/04_evi_plausibility.ipynb
```
Evaluates whether mapped woody transitions are supported by Landsat-derived seasonal EVI change.

5️⃣ **Wetlands Insight Tool case study**
```text
scripts/05_wetlands_insight_tool_case_study.ipynb
```
Generates WIT time-series outputs and normalized wetland composition plots for a selected case-study wetland.

6️⃣ **Plot encroachment and retreat trends**
```text
scripts/06_plot_encroachment_retreat_trends.ipynb
```
Produces sub-region trend plots for 5-year intervals and hydrological periods.


7️⃣ **Plot river gauge water-level time series**
```text
scripts/07_plot_river_gauge_water_level.ipynb
```
Generates river gauge plots used for hydrological interpretation.

8️⃣ **Plot EVI hexbin comparison**
```text
scripts/08_plot_evi_hexbin.ipynb
```
Produces the hexbin plot comparing median ΔEVI for encroachment and retreat.

---

## 📁 Data & Results Organization
Since raw rasters and outputs are large, they are **not stored in this repo**.  
Organize your local project like this:

```
data/
  ├── wetland boundaries/     # ANAE wetland shapefiles and case-study polygons
  ├── river gauge/            # River gauge CSVs or related hydrological data
  └── other_inputs/           # Any additional local input files

results/
  ├── step_1/
  ├── step_2/
  ├── step_3/
  ├── step_4/
  ├── step_5/
  └── figures/
```
⚠️ Note: `.gitignore` excludes these outputs so they don’t get pushed to GitHub.

---
## 📊 Outputs
- CSV summaries of woody transition statistics.
- Stability-filtered wetland summaries.
- Persistent-water mask summaries.
- Case-study rasters for selected wetlands.
- EVI plausibility summary tables.
- Wetlands Insight Tool CSV and plot outputs.
- Publication-ready figures including:
-    encroachment and retreat trend plots
-    river gauge plots
-    EVI hexbin plots
---
