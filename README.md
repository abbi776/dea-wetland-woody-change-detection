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
