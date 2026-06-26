# Dust-plume-event-monitoring-using-Multi-source-satellite-data-and-ML-model-analysis
Google Earth Engine and Python workflows for dust plume event monitoring using MODIS, Sentinel-5P, ERA5, NOAA HYSPLIT, and Random Forest model analysis.

## Overview

This study investigates a dust plume event over the Indian region during **26 May–03 June 2026** by integrating remote sensing observations, meteorological parameters, atmospheric transport modelling, and machine learning. The workflow combines satellite-derived aerosol products, ERA5 reanalysis data, NOAA HYSPLIT back trajectories, and Random Forest regression to analyse dust transport and predict Aerosol Optical Depth (AOD).

## Repository Structure

```
.
├── GEE_Scripts/
│   ├── MODIS_MAIAC_AOD.js
│   ├── Sentinel5P_AerosolIndex.js
│   └── ERA5_Meteorological_Parameters.js
│
├── Python/
│   └── RandomForest_AOD_Prediction.py
│
├── Figures/
│
├── Results/
│   ├── Feature_Importance.csv
│   ├── Feature_Importance.png
│   └── Observed_vs_Predicted.png
├── requirements.txt
└── Data Availability
```

## Datasets

The study utilizes the following publicly available datasets:

| Dataset                   | Source                              | Purpose                                                                      |
| ------------------------- | ----------------------------------- | ---------------------------------------------------------------------------- |
| MODIS MAIAC AOD           | Google Earth Engine                 | Aerosol Optical Depth                                                        |
| Sentinel-5P Aerosol Index | Google Earth Engine                 | Absorbing Aerosol Index                                                      |
| ERA5 Hourly Reanalysis    | Google Earth Engine                 | Temperature, Relative Humidity, Surface Pressure, Wind Speed, Wind Direction |
| MODIS True-Colour Imagery | NASA Worldview Snapshots            | Dust plume visualization                                                     |
| NOAA HYSPLIT              | NOAA Air Resources Laboratory (ARL) | Backward air-mass trajectory analysis                                        |

## Methodology

The study follows the workflow below:

1. Download satellite and meteorological datasets using Google Earth Engine.
2. Generate MODIS true-colour imagery from NASA Worldview.
3. Obtain backward air-mass trajectories using NOAA HYSPLIT.
4. Preprocess and reproject all raster datasets to a common spatial reference.
5. Integrate aerosol and meteorological variables into a unified dataset.
6. Train a Random Forest regression model to predict MODIS Aerosol Optical Depth (AOD).
7. Evaluate model performance using R², RMSE, and MAE.
8. Analyse feature importance to identify the dominant variables influencing AOD.

## Machine Learning Model

**Model:** Random Forest Regressor

**Target Variable**

* MODIS Aerosol Optical Depth (AOD)

**Predictor Variables**

* Sentinel-5P Aerosol Index (AI)
* Temperature
* Relative Humidity (500 hPa)
* Relative Humidity (850 hPa)
* Surface Pressure
* Wind Speed
* Wind Direction

## Software Requirements

* Python 3.x
* Google Earth Engine
* Google Colab
* ArcGIS

Required Python packages:

```
numpy
pandas
rasterio
matplotlib
scikit-learn
```

Install dependencies using:

```bash
pip install -r requirements.txt
```

## Results

The Random Forest model demonstrated strong predictive capability for AOD estimation using satellite-derived aerosol information and meteorological parameters. Feature importance analysis identified Aerosol Index and Temperature as the most influential predictors of AOD variability during the study period.

## Data Availability

The datasets used in this study are publicly available through Google Earth Engine, NASA Worldview Snapshots, and the NOAA Air Resources Laboratory (NOAA-ARL) HYSPLIT model.


