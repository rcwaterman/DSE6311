# DSE6311 - Predicting Thermal Error in High Accuracy Accelerometers
## Background
Accelerometers embedded in Inertial Measurement Units (IMU's) are subject to erroneous output due to internal stresses from thermal expansion and contraction. IMUs, particularly in Integrated Circuit (IC) form, are ubiquitous in embedded systems from drones to phones, serving the critical function of measuring 6 degree-of-freedom motion. In highly precise applications, error in the accelerometer measurement as a result of thermal variance can lead to system level performance issues. 
## Question
Can a machine learning model accurately predict cartesian axis measurement error due to thermal fluctuation, effectively correcting this failure mode?   
## Hypothesis and Predictions
- Hypothesis: The relationship between thermal energy and axial stress is a function of the substrate surface area/geometry, which is predictable and consistent in this application.  
- Prediction: Given enough clean data, a model can sufficiently predict the offset vector required to cancel error due to thermal drift. 

## Repository Contents
- `data/` - Resampled one-second sensor CSVs (temperature channels and x/y/z acceleration error) covering 2023-01-31 through 2023-04-14.
- `EDA/` - Descriptive statistics, missingness and collinearity checks, PCA, and an initial naive GLM baseline.
- `Preprocessing_and_FE/` - Chronological train/test splitting, predictor standardization, and feature engineering.
- `Baseline_Models/` - Non-neural baselines: mean, persistence, rolling-mean, and drift predictors, plus linear regression, Ridge, ElasticNet, PLS, KNN, random forest, extra trees, and histogram gradient boosting.
- `Hyperparameter_Tuning/` - LSTM sequence models tuned over walk-forward fold counts and sequence lengths, evaluated with both uninterrupted-series and chunk-based (discrete-chunk) validation schemes, and compared against a persistence baseline.
- `reports/` - Written deliverables (EDA, preprocessing/FE, baseline model, and hyperparameter tuning reports) corresponding to each notebook stage.

## Requirements
- Python 3.13
- Dependencies listed in `requirements.txt` (install with `pip install -r requirements.txt`); key libraries include pandas, numpy, scikit-learn, tensorflow, matplotlib, and seaborn.
- Notebooks expect the CSV files in `data/` to remain in place; paths are resolved relative to each notebook's parent directory. Data can be found [here](https://data.mendeley.com/datasets/f78bmhr628/1).