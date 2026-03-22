# DataQuest 2026

Run project with `./run-jupyter.sh`

# Hospital Readmission Prediction

A machine learning pipeline to predict whether a diabetic patient will be readmitted to hospital, supporting early clinical intervention and resource planning.

---

## Business Problem

Unplanned readmissions strain hospital budgets, occupy scarce beds, and worsen patient outcomes. This project predicts binary readmission risk — **readmitted vs not readmitted** — enabling clinicians to intervene before high-risk patients are discharged.

---

## Dataset

**UCI Diabetes 130-US Hospitals (1999–2008)**
101,766 patient encounters across 130 US hospitals.

---

## Technical Stack

| Area | Tools |
|---|---|
| Language | Python 3.13 |
| Data processing | Polars, Pandas |
| Machine learning | Scikit-learn, XGBoost |
| Dimensionality reduction | PCA, Feature Importance Selection |
| Storage | Parquet |
| Environment | uv, Jupyter |

---

## Project Structure

```
.
├── data/
│   ├── scaled/          # preprocessed scaled features
│   └── selected/        # feature importance selected features
├── model/
│   ├── xgboost_model.json
│   └── results/
├── 01_preprocessing/
│   ├── 01_analysis.ipynb
│   └── 02_cleaning.ipynb
├── 02_splitting/
│   └── 01_splitting.ipynb
├── 03_training/
│   └── xgboost.ipynb
├── diabetic_data.csv
└── README.md
```

---

## Pipeline

```
Raw data → Clean → Encode → Scale → Split → Feature Selection → Train → Evaluate
```

1. Replace missing values, drop high-missing and zero-variance columns
2. One Hot encode remaining categoricals
3. Scale numerical features with `RobustScaler`
4. Split: 70% train / 30% test — stratified
5. Reduce features via XGBoost feature importance
6. Train XGBoost binary classifier
7. Evaluate on held-out test set

---

Run notebooks in this folder order: 01_preprocessing → 02_splitting → 03_training

---

## Data Source

Strack et al. (2014). *Impact of HbA1c Measurement on Hospital Readmission Rates.* BioMed Research International. https://doi.org/10.1155/2014/781670
