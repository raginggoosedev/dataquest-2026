# DataQuest 2026

Run project with `./run-jupyter.sh`

A machine learning pipeline to predict whether a diabetic patient will be readmitted to hospital, helping healthcare providers identify high-risk patients early and allocate resources more effectively.

---

## Business Problem

Unplanned hospital readmissions are a significant cost driver in healthcare — both financially and in patient outcomes. Early identification of high-risk patients allows clinical teams to intervene before discharge, improving care quality and reducing avoidable readmissions.

This project predicts one of three outcomes for each patient encounter:

| Outcome | Meaning |
|---|---|
| Not readmitted | Low risk — standard discharge |
| Readmitted after 30 days | Moderate risk — follow-up recommended |
| Readmitted within 30 days | High risk — intervention needed |

---

## Dataset

**UCI Diabetes 130-US Hospitals (1999–2008)** — 101,766 patient encounters across 130 US hospitals, covering demographics, diagnoses, medications, and hospital visit history.

---

## Technical Stack

| Area | Tools |
|---|---|
| Language | Python 3.13 |
| Data processing | Polars, Pandas |
| Machine learning | Scikit-learn |
| Storage | Parquet (via PyArrow) |
| Environment | uv, Jupyter |

---

## Project Structure

```
.
├── Data/
│   ├── train.parquet
│   ├── dev.parquet
│   ├── val.parquet
│   └── test.parquet
├── notebooks/
│   └── preprocessing.ipynb
├── diabetic_data.csv
└── README.md
```

---

## Getting Started

```bash
uv add polars scikit-learn pandas pyarrow jupyter
```

Run `notebooks/preprocessing.ipynb` to reproduce the full pipeline.

---

## Data Source

Strack et al. (2014). *Impact of HbA1c Measurement on Hospital Readmission Rates.* BioMed Research International. https://doi.org/10.1155/2014/781670
