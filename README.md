# UrbanIntelligence

UrbanIntelligence is a geospatial machine learning project that leverages satellite-derived NDVI time-series data to classify land cover types and model urban growth. It aims to assist urban planners, policymakers, and researchers by analyzing how cities have expanded over time and predicting potential future development zones.

---

## Overview

This project classifies land cover types and models urban growth trends using NDVI signals derived from remote sensing. It applies logistic regression to handle noisy, time-series satellite imagery and outputs a city-wise Urban Growth Index, change detection reports, and spatial forecasts of urban sprawl.

---

## Objectives

- Classify land cover types: Water, Impervious, Farm, Forest, Grass, Orchard.
- Track temporal land cover transitions to understand urbanization patterns.
- Predict future urban expansion zones using NDVI trends.
- Generate a city-level Urban Growth Index.
- Provide statistical and visual reports to summarize city development.

---

## Dataset

### Structure

Each row in the dataset includes:

- `ID`: Unique identifier for the location.
- `class`: Ground truth land cover label.
- `YYYYMMDD_N`: NDVI values across 27 time points (from satellite imagery).

### Sources

- NDVI: Derived from Landsat/Sentinel satellite imagery.
- Land cover labels: Extracted from OpenStreetMap polygons.
- Optional: Population grids, road density, and elevation data for extended analysis.

---

## Methodology

### 1. Data Preprocessing

- Imputation of missing NDVI values caused by cloud cover.
- Denoising through smoothing/filtering.
- Normalization and scaling of time-series inputs.

### 2. Feature Engineering

- Extract statistics from NDVI signals: mean, std, peak, seasonal variance.
- Use temporal changes to capture vegetation dynamics.

### 3. Modeling

- Multiclass logistic regression (baseline model).
- Model trained to classify land cover based on NDVI time-series signals.

### 4. Forecasting

- Analyze historical transition patterns (e.g., forest → impervious).
- Predict potential urban growth zones using learned trends.
- Assign Urban Growth Index based on historical expansion rates.

### 5. Reporting

- Produce land cover classification maps.
- Compute growth metrics per city.
- Generate CSV predictions in the following format:
---

## Use Cases

- Track urban development over years or decades.
- Compare growth trends across cities or districts.
- Support data-driven city planning and zoning decisions.
- Integrate with GIS tools for real-time urban monitoring.

---

## Technologies

- **Language**: Python 3.11
- **Libraries**:
  - `pandas`, `numpy` for data handling
  - `scikit-learn` for machine learning (logistic regression)
  - `matplotlib`, `seaborn`, `plotly` for visualization
  - (Optional) `GeoPandas`, `Folium`, `Kepler.gl` for spatial mapping

---

## Future Work

- Apply deep learning (LSTMs, CNNs) to improve long-term prediction accuracy.
- Add real-time population or infrastructure data for richer analysis.
- Build a web dashboard for interactive visualization.
- Scale up to national or continental land use mapping.

---

## License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute the code with proper attribution.

---

## Acknowledgements

- Satellite NDVI Data: USGS Landsat & Copernicus Sentinel
- Land Cover Labels: OpenStreetMap contributors
- Hackathon: Summer Analytics 2025 – First Course Track (IIT Roorkee + GeeksForGeeks)
