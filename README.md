# UrbanIntelligence
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
