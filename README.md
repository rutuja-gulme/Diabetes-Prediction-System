# Diabetes Prediction using K-Nearest Neighbors (KNN)

## Overview

A Python-based healthcare analytics project that uses K-Nearest Neighbors (KNN) classification to predict whether a patient has diabetes based on diagnostic measurements.

The target variable is binary: Diabetic (1) or Non-Diabetic (0).

## Key Features

- Class distribution analysis of diabetic vs non-diabetic records
- Feature correlation analysis to identify key health factors
- Hyperparameter tuning using 5-Fold Cross-Validation to select optimal K
- Binary classification using K-Nearest Neighbors (KNN)
- Generation and export of test predictions to CSV format

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Project Workflow

1. Load training and testing datasets using Pandas.
2. Plot a bar graph to analyze class distribution of target outcomes.
3. Generate a correlation heatmap to analyze relationships between features (e.g., Glucose, BMI).
4. Evaluate odd K values from 1 to 25 using 5-Fold Cross-Validation.
5. Train the final KNN model with optimal K (K = 15).
6. Predict outcomes for test data (`Diabetes_Xtest.csv`) and export to `Diabetes_Predictions.csv`.

## Project Structure

```text
diabetes-prediction-system/
├── diabetes_prediction_analysis.ipynb
├── Diabetes_XTrain.csv
├── Diabetes_YTrain.csv
├── Diabetes_Xtest.csv
├── Diabetes_Predictions.csv
├── requirements.txt
├── README.md
└── .gitignore
