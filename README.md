# alau-dam-inundation-model-
# MSc title "Dam-Breach Inundation Modelling Using a Neighbourhood-Based Fill-and-Spill Inundation Model: A Case Study of Alau Dam, Maiduguri, Nigeria"

# Dam-Breach Inundation Modelling Workflow (Alau Dam, Nigeria)

[![Python](https://shields.io)](https://python.org)
[![Geospatial](https://shields.io)](https://qgis.org)
[![License: MIT](https://shields.io)](https://opensource.org)

This repository contains the reproducible geospatial data pipeline and hydrological modeling workflow developed for my Master of Science thesis at the **University of Twente**. 

The workflow implements a custom, open-data Python framework to evaluate scenario-based dam-breach inundation screening, using the September 2024 failure event of the Alau Dam in Maiduguri, Nigeria as a primary case study.

---

## 🏫 Academic Context

*   **Institution:** [Faculty of Geo-Information Science and Earth Observation (ITC)](https://itc.nl), University of Twente, Enschede, The Netherlands
*   **Degree:** M.Sc. Geoinformation Science and Earth Observation (Water Resources and Environmental Management)
*   **Thesis Title:** *Dam-Breach Inundation Modelling Using a Neighbourhood-Based Fill-and-Spill Inundation Model: A Case Study of Alau Dam, Maiduguri, Nigeria*
*   **Academic Supervisor:** [Dr. B.H.P. Maathuis](mailto:b.h.p.maathuis@utwente.nl) (Assistant Professor / Project Manager, Faculty ITC)
*   **Defense Date:** August 26, 2026

---

## 🛠️ Methodology & Technical Highlights

*   **Custom Simulation Engine:** Built a neighborhood-based, 8-neighbor breadth-first-search (BFS) "fill-and-spill" inundation model using pure Python.
*   **Terrain Data Comparison:** Analyzed and processed Copernicus DEM GLO-30 and FABDEM variants (r = 0.9986; RMSE = 0.63 m) to evaluate local flow connectivity alterations.
*   **Satellite Validation:** Evaluated simulated flood footprints against Sentinel-1, Sentinel-2, and Copernicus EMS (EMSR753) reference masks using strict performance indicators (Precision, Recall, F1-Score, CSI/IoU, and area bias).
*   **Uncertainty Quantification:** Performed one-at-a-time (OAT) parameter sensitivity analysis with explicit uncertainty limit interpretations.

---

## 📂 Repository Structure

The code is organized to maintain reproducibility and clean data provenance:

```text
├── notebook/
│   └── Alau_Dam_Breach_Inundation_Modelling_v9.ipynb  <- Authoritative analytical notebook
├── datasets/
│   ├── conditioned_dems/                              <- Hydro-conditioned, preprocessed rasters
│   ├── dems/                                          <- Source DEM tiles (Copernicus / FABDEM)
│   ├── satellite/                                     <- Sentinel-1 & Sentinel-2 input footprints
│   └── c_EMSR753_flood_event/                         <- Copernicus EMS shapefile data
└── alau_dam_inundation_outputs/                       <- Output root for generated products
    ├── model_outputs/                                 <- Low/Med/High scenario depth & mask layers
    ├── figures/                                       <- Validated susceptibility and maps
    └── tables/                                        <- Extracted validation metrics (CSV)
```

---

## 🚀 Running the Workflow

### 1. Prerequisites
The workflow requires a standard scientific Python environment. Ensure you have the following geospatial libraries installed:
```bash
pip install numpy geopandas rasterio matplotlib jupyter
```

### 2. Preprocessing Note
Initial DEM conditioning (projection, river burning, and sink filling) was conducted inside the **ILWIS (Integrated Land and Water Information System)** desktop environment to prepare the hydro-enforced terrain models. The final automated simulation and validation stages run strictly within the Python environment via the Jupyter Notebook.

### 3. Execution
1. Clone this repository.
2. Launch Jupyter Notebook and open: `notebook/Alau_Dam_Breach_Inundation_Modelling_v9.ipynb`.
3. The script will automatically resolve the root directories and execute the cell blocks sequentially.

---

## 📜 License & Citation

The code and programmatic workflows contained in this repository are licensed under the **MIT License**. 

If you use this model or refer to the methodological findings in an academic context, please cite the underlying thesis:

> **Edeh, C. J. (2026).** *Dam-Breach Inundation Modelling Using a Neighbourhood-Based Fill-and-Spill Inundation Model: A Case Study of Alau Dam, Maiduguri, Nigeria.* M.Sc. Thesis, Faculty of Geo-Information Science and Earth Observation (ITC), University of Twente.

---
📧 **Contact:** [Chioma Joy Edeh](mailto:c.j.edeh25@gmail.com) — [LinkedIn](https://linkedin.com/in/chioma49edeh)

