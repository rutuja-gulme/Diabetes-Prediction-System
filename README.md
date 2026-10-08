# Diabetes Classification & Risk Analysis using KNN

## 1. Executive Summary
Early diagnosis of diabetes is critical for mitigating long-term risks such as cardiovascular disease and kidney failure. This project establishes an end-to-end classification pipeline to identify whether a patient is at risk of diabetes based on diagnostic biomarkers. 

Using supervised machine learning (**K-Nearest Neighbors**), the project identifies key physiological risk indicators, optimizes model performance via stratified 5-fold cross-validation, and scores unseen clinical observations.

---

## 2. Business & Clinical Objectives
- **Target Audience**: Healthcare analytics teams, clinical triage specialists.
- **Primary Goal**: Accurately predict patient diabetes outcome (`Outcome = 1` vs `Outcome = 0`) using non-invasive diagnostic metrics.
- **Key Deliverable**: Validated model and batch predictions exported as `Diabetes_Predictions.csv` for downstream reporting.

---

## 3. Dataset & Feature Schema
The dataset consists of diagnostic measures collected from female patients:

| Feature | Description | Clinical Relevance |
| :--- | :--- | :--- |
| **Pregnancies** | Number of pregnancies | Tracks gestational diabetes history |
| **Glucose** | 2-hour plasma glucose concentration (mg/dL) | Primary indicator of insulin resistance |
| **BloodPressure** | Diastolic blood pressure (mm Hg) | Associated cardiovascular risk marker |
| **SkinThickness** | Triceps skin fold thickness (mm) | Metric for body fat distribution |
| **Insulin** | 2-hour serum insulin (mu U/ml) | Direct marker of pancreatic response |
| **BMI** | Body mass index (weight / height²) | Obesity and metabolic syndrome marker |
| **DiabetesPedigreeFunction** | Family history score | Genetic predisposition metric |
| **Age** | Patient age in years | Age-related risk progression |
| **Outcome** | Class label (Target) | `0` = Non-Diabetic, `1` = Diabetic |

---

## 4. End-to-End Pipeline & Analytical Methodology

### Step 1: Exploratory Data Analysis & Class Balance
- Inspected training cohort (576 observations): **375 Non-Diabetic (65.1%)** vs **201 Diabetic (34.9%)**.
- Assessed class imbalance to ensure baseline performance targets exceed the 65.1% majority class baseline.

### Step 2: Correlation & Feature Interaction
- Conducted multivariate correlation analysis.
- Found **Glucose** and **BMI** to have the strongest positive linear association with diabetes diagnosis.

### Step 3: Hyperparameter Tuning ($K$-Selection)
- Evaluated odd neighbor values ($K \in [1, 25]$) to eliminate decision-boundary ties.
- Implemented **5-Fold Cross-Validation** to minimize variance and guard against overfitting.
- **Optimal Hyperparameter**: $K = 15$ yielded peak cross-validation accuracy of **~73.4%**.

### Step 4: Model Training & Batch Inference
- Fitted the final `KNeighborsClassifier(n_neighbors=15)` on the full training partition.
- Inferred target labels for 192 unseen test observations (`Diabetes_Xtest.csv`).
- Structured and exported predictions to `Diabetes_Predictions.csv`.

---

## 5. Key Analytical Takeaways
1. **Glucose as Lead Metric**: Patients presenting elevated glucose levels exhibited significantly higher probability of positive diagnosis, affirming fasting/tolerance blood sugar as primary diagnostic triage criteria.
2. **Metabolic Interplay**: Interaction between BMI and Age compounded risk, suggesting combined lifestyle interventions yield the highest clinical benefit.
3. **Algorithmic Viability**: At ~73.4% cross-validation accuracy, the non-parametric KNN approach provides a reliable, interpretable baseline for exploratory patient screening.

---

## 6. Repository Architecture

```text
diabetes-prediction-system/
│
├── diabetes_prediction_analysis.ipynb   # Complete analysis & model execution
├── Diabetes_XTrain.csv                  # Training features (576 rows)
├── Diabetes_YTrain.csv                  # Training target outcomes (576 rows)
├── Diabetes_Xtest.csv                   # Test features (192 rows)
├── Diabetes_Predictions.csv             # Model output predictions
├── requirements.txt                     # Reproducible environment dependencies
├── README.md                            # Project documentation
└── .gitignore                           # Ignored environment artifacts
