# Diabetes Prediction System using Machine Learning

## Project Overview
A healthcare machine learning classification project designed to predict whether a patient has diabetes based on diagnostic measurements. The model identifies key physiological indicators such as glucose levels, BMI, and age to assess metabolic disease risks.

## Key Highlights & Results
- **Model Evaluation**: Evaluated K-Nearest Neighbors (KNN) classification across varying hyperparameter configurations.
- **Predictive Performance**: Achieved optimal classification performance using 5-fold cross-validation at K = 15.
- **Key Risk Indicators**: Exploratory data analysis and correlation heatmaps revealed strong relationships between Glucose levels, BMI, and diabetes onset.
- **Automated Inference**: Successfully generated predictions on unseen test records and exported output directly to CSV format.

## Technical Stack
- **Language**: Python
- **Libraries**: Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn
- **Algorithm**: K-Nearest Neighbors (KNN)
- **Environment**: Jupyter Notebook

## Dataset Description
The clinical dataset contains diagnostic measurements for patient records:
- **Pregnancies**: Number of times pregnant
- **Glucose**: Plasma glucose concentration (2 hours in an oral glucose tolerance test)
- **BloodPressure**: Diastolic blood pressure (mm Hg)
- **SkinThickness**: Triceps skin fold thickness (mm)
- **Insulin**: 2-Hour serum insulin (mu U/ml)
- **BMI**: Body mass index (weight in kg/(height in m)²)
- **DiabetesPedigreeFunction**: Diabetes pedigree score based on genetic family history
- **Age**: Patient age in years
- **Outcome**: Binary diagnostic target (0: Non-Diabetic, 1: Diabetic)

## Project Structure

```text
Diabetes-Prediction-System/
├── diabetes_prediction_analysis.ipynb
├── Diabetes_XTrain.csv
├── Diabetes_YTrain.csv
├── Diabetes_Xtest.csv
├── Diabetes_Predictions.csv
├── requirements.txt
├── .gitignore
└── README.md
```

## How to Run Locally

1. Clone this repository:
git clone https://github.com/rutuja-gulme/Diabetes-Prediction-System.git
cd Diabetes-Prediction-System

2. Install dependencies:
pip install -r requirements.txt

3. Launch Jupyter Notebook and run all cells:
jupyter notebook diabetes_prediction_analysis.ipynb

## Clinical & Healthcare Impact
This screening tool helps healthcare professionals identify high-risk individuals early, enabling proactive dietary interventions and clinical lifestyle management before severe complications develop.
