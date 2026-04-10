# Physics-Informed Full-Sequence Prediction of Nearshore Wave Time Series

This repository contains the final AAI-590 capstone project for staged surrogate modeling of nearshore wave time series from offshore FUNWAVE-TVD forcing.

## Project summary
The project builds and compares three offshore-to-local surrogate models:
1. A spectral ridge baseline
2. A full-sequence conditional temporal convolutional network (TCN)
3. A physics-informed residual hybrid that adds differentiable travel-time and shoaling structure

The final capstone experiment uses 5,000 stationized FUNWAVE-TVD runs and evaluates held-out performance with RMSE, MAE, correlation, mean absolute lag, and spectral-band energy error.

## Main result snapshot
On the held-out test split, the physics-informed hybrid achieved:
- RMSE = 0.086
- MAE = 0.065
- Correlation = 0.891
- Mean absolute lag = 0.231 s

A key interpretation from the depth-binned analysis is that mean sample-wise R^2 deteriorates as the target stations approach the very shallow near-dry regime. The model still works well through most of the profile, and the negative global R^2 is concentrated in the shallowest bin rather than across the whole dataset.

## Repository structure
- `funwave_capstone_station_fullsequence_pipeline_v2.ipynb` — main end-to-end notebook
- `funwave_capstone_report_support_from_saved_artifacts.ipynb` — report-support notebook
- `AAI590_capstone_report_final_v2.pdf` — final written report
- `AAI590_capstone_presentation_final_v2.pdf` — final slide deck

## Data expectations
The main notebook recursively discovers `.nc` files under the configured data root and can also extract `.nc` files from `.zip` archives. The zip-safe version prevents collisions when identical run names appear in different archives.

The raw data in .zip format can be found here: https://drive.google.com/drive/folders/1qe8QBZ-wqBaKf7n3wV7q9pqRZpMrcIlk?usp=sharing 

## Reproducibility notes
- The capstone-default profile is designed to be local-PC and Colab friendly.
- Preprocessing caches station-level artifacts to avoid repeated NetCDF parsing.
- The final stationization logic uses one offshore station and ten shoreward target stations per run.
- Full sequences are preserved deliberately; no sliding windows are used.