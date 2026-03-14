# Vaccine Hesitancy in India : ML-Based Prediction Framework

> **Research project presented at Young Researchers' Conference 2025**
> Organized by AAAI Student Chapter of Pimpri Chinchwad College of Engineering · Dept. of CSE (AI&ML)

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.3+-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-1.7+-189A4B?style=flat)
![imbalanced-learn](https://img.shields.io/badge/imbalanced--learn-SMOTE-blueviolet?style=flat)
![Conference](https://img.shields.io/badge/YRC%202025-PCCOE-orange?style=flat)

---

## Overview

Vaccine hesitancy — the reluctance or refusal to vaccinate despite availability — was identified by the WHO as one of the **top ten threats to global health** in 2019. Despite India administering over **2.21 billion COVID-19 doses**, hesitancy persists, shaped by socioeconomic factors, misinformation, and lack of trust in institutions.

This project applies a **comparative machine learning framework** on **primary survey data collected from Indian respondents** to:
- Predict whether an individual is likely to be vaccine-hesitant
- Identify the most important determinants of hesitancy
- Provide interpretable, actionable insights for public health strategies


## Research Highlights

| Aspect | Details |
|--------|---------|
| **Data** | Primary survey (structured questionnaire, India-specific) |
| **Target** | Binary: Hesitant vs. Non-Hesitant |
| **Class Imbalance** | Handled using SMOTE |
| **Models Compared** | Logistic Regression, Decision Tree, Random Forest, XGBoost (GBDT) + Voting Ensemble |
| **Best Model** | Random Forest — **84.6% Accuracy, F1 = 0.84** |
| **Presented at** | Young Researchers' Conference 2025, PCCOE (Dept. of CSE AI&ML) |

## Methodology

```
Structured Survey (India)
        ↓
Preprocessing (OrdinalEncoder + One-Hot Encoding + StandardScaler)
        ↓
Class Balancing (SMOTE)
        ↓
Model Training & Hyperparameter Tuning (GridSearchCV / RandomizedSearchCV)
        ↓
Evaluation (Accuracy, Precision, Recall, F1, Confusion Matrix)
        ↓
Feature Importance Analysis
```

## Model Results

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Logistic Regression | 75.47% | 0.79 | 0.75 | 0.72 |
| Decision Tree | 69.81% | 0.69 | 0.70 | 0.69 |
| Gradient Boosting (XGBoost) | 73.58% | 0.73 | 0.74 | 0.73 |
| **Random Forest** | **84.62%** | **0.86** | **0.85** | **0.84** |
| Voting Ensemble (RF + XGB) | 82.05% | — | — | — |

> Random Forest outperformed all other models across all metrics.

---

## Top Determinants of Vaccine Hesitancy

Based on Random Forest feature importances:

1. **Trust in Doctors/Healthcare Workers** — single highest predictor
2. **Education Level** — strong inverse relationship with hesitancy
3. **Trust in Government (Health Ministry)** — significant influence
4. **Past Vaccination History** (polio, BCG, MMR, etc.)
5. **Healthcare proximity** (working in or near healthcare)
6. **Monthly Household Income**
7. **Prior COVID-19 Exposure** (self or family)
8. **Social influence** (trust in friends & family)

---

## Repository Structure

```
vaccine-hesitancy-india/
│
├── notebooks/
│   ├── logistic_regression.ipynb      # LR with GridSearchCV + SMOTE
│   └── random_forest_xgboost.ipynb    # RF + XGBoost + Voting Ensemble
│
├── data/
│   └── README.md                      # Dataset description & collection methodology
│
├── results/
│   └── README.md                      # Summary of all results & visualizations
│
├── requirements.txt                   # Python dependencies
├── .gitignore
└── README.md
```

---

## Setup & Usage

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/vaccine-hesitancy-india.git
cd vaccine-hesitancy-india
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Add the dataset
Place your CSV file at:
```
data/Vaccine_Hesitancy_Research_Clean.csv
```
> See `data/README.md` for the full list of survey questions and column descriptions.

### 4. Run the notebooks
Open in Jupyter or Google Colab:
- `notebooks/logistic_regression.ipynb`
- `notebooks/random_forest_xgboost.ipynb`


## Features Used

The survey captured 18 features across four categories:

**Socio-demographic:** Age, Gender, Area type, Education, Employment status, Monthly household income

**Health background:** Chronic conditions, COVID-19 history, Healthcare proximity, Prior vaccination history

**Trust factors:** Trust in doctors, government health bodies, friends & family

**Attitudes:** Belief in vaccine safety, effectiveness, side-effect worry, wait-and-see tendency

**Motivational:** What would increase likelihood of vaccination

---

## Research Context

Prior studies on vaccine hesitancy focused on US, China, or Europe, and relied heavily on social media data (Twitter, Reddit). These approaches excluded offline/rural populations and lacked interpretability.

**Our contribution:** An India-specific, survey-based ML framework that:
- Uses structured primary data (not social media)
- Integrates demographics + attitudes + trust factors together
- Applies SMOTE for class fairness
- Balances accuracy with model interpretability
- Covers all vaccines, not just COVID-19

---

## Authors

| Name | Role |
|------|------|
| Anuska Misra | Research & Implementation |
| Shruti Jahagirdar | Research & Implementation |
| Sharayu Kotkar | Research & Implementation |

**Guide:** Prof. Pallavi Dhade
**Institution:** Pimpri Chinchwad College of Engineering, Dept. of CSE (AI&ML)
**Conference:** AAAI Student Chapter — Young Researchers' Conference 2025

---

## Citation

```
Misra, A., Jahagirdar, S., & Kotkar, S. (2025). Uncovering determinants of vaccine hesitancy
in India: A comparative machine learning framework for data-driven insights.
Young Researchers' Conference 2025, Dept. of CSE (AI&ML), PCCOE.
```

---

## Dataset Note

The survey was fully anonymous — no personally identifiable information was collected. The cleaned dataset is included in data/ and can be used freely for research and learning purposes.
