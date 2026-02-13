# Applied Data Science (DSC-450) | Project 02
🩺CLINICAL DATA REMEDIATION
---
**Team Members:** Christian Shannon, Ashley Love, Mugtaba Awad, and Kirsten Livingston

---
## Project Overview

In healthcare informatics, data integrity is a prerequisite for patient safety and hospital efficiency. The Diabetes 130-US Hospitals dataset, representing a decade of clinical care, contains significant “noise”, specifically non-standardized medical codes and missing demographic markers (Strack et al., 2024). The team hypothesized that a modular, automated remediation pipeline would outperform traditional manual cleaning by providing a statistically sound, reproducible method for handling missingness. The primary objective was to improve the DQI –encompassing completeness, validity, and consistency. Thereby creating a reliable asset for predicting hospital readmission (Pipino et al., 2002). 

---
## 🪜Project Workflow

|Stage (Notebook)                      | Description                         |
|--------------------------------------|-------------------------------------|
| Phase 1- Clinical Audit & Wrangling  | Quantitative data audit             |
| Phase 2- Advanced Remediation        | MICE imputation & Iterative Imputer |
| Phase 3- Visual Validation           | Mdical plausibility using KDE plots |

---
## 🟰Results:

### 👥Business Impact
The automated remediation pipeline successfully achieved the target 25% improvement in Data Quality Index (DQI), demonstrating measurable gains in completeness, validity, and consistency across clinical records.

Final exploratory analysis revealed an 11.2% hospital readmission rate, with the highest-risk concentrations occurring among geriatric patient populations.

This modular framework provides clinical stakeholders with a scalable approach to combating data decay, ensuring that predictive models are trained on standardized, medically reliable patient records rather than incomplete or fragmented data.


### 🔑Key Findings
1. **DQI Improvement:** The remediation workflow produced a quantified 25% increase in overall data quality, validating the effectiveness of the automated pipeline.

2. **High Missingness Identified:** Nearly 97% of patient weight values were missing due to sentinel null placeholders (e.g., “?”), requiring advanced imputation rather than deletion.

3. **Clinical Validity Preserved:** Out-of-range laboratory values and non-standard clinical entries were flagged through auditing logic to ensure downstream modeling is medically plausible.

4. **Consistency Strengthened:** ICD-9 diagnosis codes were normalized using Regular Expressions, preventing categorical fragmentation across hospital encounter records.

---
## 🔨Technical Stack
    Data Wrangling: pandas, NumPy
    Data Remediation: Scikit-Learn (IterativeImputer), Regex normalization
    Visualization: Matplotlib, Seaborn
    Environment: Python 3.x, Jupyter Notebook, GitHub Pages deployment
    
---
## ⚖️Ethical Considerations
- Patient data anonymized — no personal identifiers included
- Pipeline designed for transparency
- Remediation methods aimed at improving predictive integrity, not manipulating outcomes

