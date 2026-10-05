# 🩺 Diabetes Prediction & Clinical Risk Analysis

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/)
[![Machine Learning](https://img.shields.io/badge/Machine%20Learning-KNN%20Classifier-green.svg)](https://scikit-learn.org/)
[![Libraries](https://img.shields.io/badge/Libraries-Pandas%20%7C%20NumPy%20%7C%20Seaborn%20%7C%20Scikit--Learn-orange.svg)]()

## 📌 Project Overview
Diabetes is a chronic metabolic condition that significantly impairs the body's ability to process blood glucose, posing risks of severe complications such as cardiovascular disease and stroke. 

This project implements an end-to-end **Supervised Binary Classification** pipeline using the **K-Nearest Neighbors (KNN)** algorithm. It aims to predict whether a patient is diabetic (`Outcome = 1`) or non-diabetic (`Outcome = 0`) based on diagnostic diagnostic biomarkers.

---

## 📊 Dataset Schema
The dataset consists of clinical diagnostic variables recorded across patients:

| Feature | Description | Metric Type |
| :--- | :--- | :--- |
| **Pregnancies** | Number of times pregnant | Discrete Count |
| **Glucose** | Plasma glucose concentration (2 hours in oral glucose tolerance test) | Continuous (mg/dL) |
| **BloodPressure** | Diastolic blood pressure | Continuous (mm Hg) |
| **SkinThickness** | Triceps skin fold thickness | Continuous (mm) |
| **Insulin** | 2-Hour serum insulin | Continuous (mu U/ml) |
| **BMI** | Body mass index | Continuous ($weight/height^2$) |
| **DiabetesPedigreeFunction** | Family history risk metric | Statistical Score |
| **Age** | Age in years | Discrete (Years) |
| **Outcome** *(Target)* | Diagnosis class: Non-Diabetic (`0`) vs. Diabetic (`1`) | Binary Target |

---

## 🔬 Analytical Workflow & Methodology

### 1. Exploratory Data Analysis (EDA)
- **Class Balance Analysis**: Evaluated target outcome distributions to assess class disparity (375 Non-Diabetic vs. 201 Diabetic training observations).
- **Multivariate Correlation**: Generated a correlation matrix to assess interactions between glucose levels, BMI, age, and diabetes risk.

### 2. Hyperparameter Optimization ($K$-Value Selection)
- Implemented **5-Fold Stratified Cross-Validation** over odd parameter bounds ($K \in [1, 25]$) to avoid ties and mitigate overfitting.
- Evaluated classification boundaries based on Euclidean distance metrics across the feature space.

### 3. Model Training & Test Set Inference
- Model trained on optimal neighbor configuration ($K = 15$) achieving strong cross-validation convergence (~73.4% accuracy).
- Generated predictions for 192 unseen patient records and exported to `Diabetes_Predictions.csv`.

---

## 📁 Repository Structure

```text
diabetes-prediction-system/
│
├── diabetes_prediction_analysis.ipynb   # Main analysis & model pipeline
├── Diabetes_XTrain.csv                  # Training features (576 records)
├── Diabetes_YTrain.csv                  # Training target outcomes (576 records)
├── Diabetes_Xtest.csv                   # Test feature set (192 records)
├── Diabetes_Predictions.csv             # Model output predictions
├── requirements.txt                     # Project dependencies
├── .gitignore                           # Ignored runtime/cache artifacts
└── README.md                            # Project documentation