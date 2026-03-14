# Results & Discussion

## Model Comparison

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Logistic Regression | 75.47% | 0.79 | 0.75 | 0.72 |
| Decision Tree | 69.81% | 0.69 | 0.70 | 0.69 |
| Gradient Boosting (XGBoost) | 73.58% | 0.73 | 0.74 | 0.73 |
| **Random Forest** | **84.62%** | **0.86** | **0.85** | **0.84** |
| Voting Ensemble (RF + XGB) | 82.05% | — | — | — |

**Winner: Random Forest** — best across all four metrics.

---

## Key Findings

### Top Predictors (Random Forest Feature Importance)
1. Trust in Doctors/Healthcare Workers *(highest importance)*
2. Education Level
3. Trust in Government Health Bodies
4. Prior Vaccination History (govt. vaccines)
5. Healthcare proximity
6. Monthly Household Income
7. COVID-19 exposure (self or family)
8. Trust in Friends & Family

### Interpretation
- **Trust is the #1 driver**: Respondents who slightly or mostly trusted doctors were significantly less hesitant.
- **Education matters**: Higher education correlated with lower hesitancy — likely due to better access to credible information.
- **Past vaccination compliance** is a strong positive predictor — those who took govt. vaccines before were less hesitant about COVID vaccines too.
- **Income & employment** play a moderate role, suggesting socioeconomic barriers also contribute.

---

## Why Random Forest Performed Best

- Handles non-linear feature interactions well
- Ensemble of trees reduces overfitting (unlike Decision Tree)
- Robust to outliers and noisy survey responses
- Built-in feature importance for interpretability

## Why SMOTE Was Necessary

The original dataset had class imbalance (more Non-Hesitant than Hesitant responses). Without SMOTE, models would bias toward predicting the majority class. SMOTE synthetically balanced classes, improving recall on the minority (Hesitant) class — critical for public health intervention targeting.
