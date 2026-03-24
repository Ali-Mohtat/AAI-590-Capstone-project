# Physics-Informed Machine Learning for Shoreline Dynamics

## Project Overview
This project develops a physics-informed machine learning framework for predicting shoreline dynamics under varying environmental conditions. The approach integrates wave-resolving numerical simulations with data-driven models to capture nonlinear nearshore processes and improve predictive efficiency relative to traditional coastal modeling methods.

The dataset is derived from FUNWAVE-TVD simulations and consists of transect-based nearshore hydrodynamic outputs. These simulations represent a wide range of wave conditions and coastal morphologies, providing a structured and physically consistent foundation for machine learning applications.

## Objectives
- Develop a reproducible data pipeline for large-scale coastal simulation data
- Perform exploratory data analysis (EDA) on transect-based hydrodynamic outputs
- Engineer physics-informed features representing nearshore processes
- Train and evaluate machine learning models for shoreline-related prediction tasks
- Establish a scalable framework for coastal forecasting and future deployment

## Dataset Description
The dataset consists of FUNWAVE-TVD transect-based simulation outputs containing time-resolved nearshore hydrodynamic variables, including:
- Free surface elevation
- Velocity components
- Bathymetry
- Wave breaking indicators

The dataset represents a large ensemble of simulations spanning diverse wave conditions and bathymetric configurations. It is used as a training and validation basis for machine learning models that approximate or enhance process-based coastal predictions.

## Methodology

### Data Processing and EDA
- NetCDF ingestion and parsing
- Metadata extraction and validation
- Quality control and consistency checks
- Statistical summaries of key variables
- Visualization of transect-scale behavior

### Feature Engineering
- Spatial alignment along transects
- Extraction of physically meaningful descriptors
- Representation of nearshore processes (e.g., wave transformation)

### Machine Learning Models
- Tree-based models: Random Forest, XGBoost
- Deep learning models: LSTM, CNN

The modeling approach follows a physics-informed strategy in which numerical simulations provide structured inputs and machine learning captures nonlinear relationships.

## Repository Structure

```
.
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
│   └── eda_notebook.ipynb
├── src/
│   ├── data_processing.py
│   ├── feature_engineering.py
│   └── modeling.py
├── outputs/
│   ├── figures/
│   └── tables/
├── docs/
│   └── report/
└── README.md
```

## Expected Outcomes
- Reduced computational cost compared to full numerical simulations
- Improved prediction of nonlinear nearshore dynamics
- Scalable and transferable shoreline forecasting framework

## Future Work
- Integration with observational datasets (buoys, surveys, satellite)
- Model deployment for operational use
- Transfer learning to additional coastal regions
- Development of monitoring and retraining pipelines

## Notes
- Dataset consists of research-grade numerical simulations
- Proper spatial and temporal alignment is critical for model performance

## Author
Ali Mohtat  
PhD Candidate – Coastal and Ocean Engineering  
M.S. Applied Artificial Intelligence  

## AI Disclosure
AI-assisted tools were used to support structuring and drafting of documentation. All content was reviewed, validated, and revised prior to submission.
