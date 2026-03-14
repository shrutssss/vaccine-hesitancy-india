# Dataset Description

## Overview

The dataset was collected through a **structured primary survey** targeting Indian respondents to study determinants of vaccine hesitancy. Responses were gathered via Google Forms and cleaned before analysis.

**File:** `Vaccine_Hesitancy_Research_Clean.csv`

The survey was **fully anonymous** — no personally identifiable information was collected. The dataset is included in this repository as-is.

---

## Target Variable

| Column | Description |
|--------|-------------|
| `Did you ever feel hesitant before taking the vaccine?` | Binary target: Yes / No |

---

## Features (18 total)

### Socio-Demographic
| Column | Type |
|--------|------|
| Age | Numeric |
| Gender | Categorical |
| Which type of area do you live in? | Categorical (Urban/Rural/Semi-urban) |
| Education | Ordinal |
| Employment status | Categorical |
| Monthly household income | Ordinal |

### Health Background
| Column | Type |
|--------|------|
| Do you or your family members have any chronic health conditions? | Binary |
| Have you or a close family member been infected with COVID-19 in the past? | Binary |
| Do you or someone close to you work in healthcare? | Binary |
| Have you taken all the previous vaccines offered by the Indian Govt.? | Binary |

### Trust in Information Sources (Likert scale)
| Column | Type |
|--------|------|
| Trust in Doctors/Healthcare workers | Ordinal |
| Trust in Government (Health Ministry / Public Health) | Ordinal |
| Trust in Friends & family | Ordinal |

### Attitudes Toward Vaccines (Likert scale)
| Column | Type |
|--------|------|
| Vaccines are safe. | Ordinal |
| Vaccines are effective in preventing serious illness. | Ordinal |
| I am worried about potential side effects from the vaccine. | Ordinal |
| I prefer to wait and see how the vaccine affects others before getting it. | Ordinal |

### Motivation
| Column | Type |
|--------|------|
| What would make you more likely to get vaccinated? | Multi-select categorical |

---

## Preprocessing Steps Applied

1. Strip whitespace from column names
2. OrdinalEncoder on `Education` and `Monthly household income`
3. `pd.get_dummies` (one-hot encoding) on remaining categorical columns
4. `StandardScaler` for feature scaling
5. SMOTE for class balancing (applied only on training data)
