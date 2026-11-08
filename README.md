# Solar PV Output Prediction and Ensemble Evaluation

**Sujung Yun · Research Intern · POSTECH SPaC Lab · January–February 2026**

This repository presents my research participation report on estimating solar photovoltaic (PV) output using plant operating records and weather data from the Korea Meteorological Administration (KMA).

📄 **[Read the full report (PDF)](./POSTECH_Research_Report_English.pdf)**

## Overview

Using records from the Yangsan solar PV plant, I implemented and evaluated Random Forest, LightGBM, and XGBoost regression models. I also incorporated KMA weather observations and evaluated an ensemble that averages the predictions of the three models with equal weights.

## My Contributions

- Converted supplied SQLite records to CSV, inspected duplicate timestamps, and merged sensor and inverter data by measurement time.
- Prepared model inputs through correlation analysis, operating-status filtering, hourly aggregation, missing-value removal, and normalization.
- Integrated KMA air temperature, wind speed, and relative humidity data and implemented model training and evaluation in Python.
- Combined predictions from saved models and compared the ensemble with individual models on the same test data.

## Key Result

On 3,602 test samples, the ensemble achieved **R² = 0.9360** and **RMSE = 0.0649**, a modest improvement over the best individual model, LightGBM (**R² = 0.9340; RMSE = 0.0659**). These RMSE values use the plant-capacity-normalized target.

The study evaluated output estimation at the same time as the input observations; future-output forecasting was not evaluated. The report also discusses differences between experimental settings and limitations in attributing performance changes to KMA data.

**Tools and methods:** Python · SQLite · Random Forest · LightGBM · XGBoost · Ensemble averaging
