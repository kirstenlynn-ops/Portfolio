# 🔮PREDICTIVE ENGAGEMENT MODELING FOR RETAIL BANKING
---
**Team Members:** Christian Shannon, Ashley Love, Mugtaba Awad, and Kirsten Livingston

**Presentation Link:**
https://www.canva.com/design/DAG9koWKaK4/vhbgQZ2pM8lB56cZI8DwKg/edit?utm_content=DAG9koWKaK4&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton

---
## Project Overview

This analysis transforms the UCI Bank Marketing dataset (41,188 records from Portuguese bank telemarketing campaigns, 2008-2010) from a term deposit subscription prediction task into a customer churn prevention framework. By reframing "no" responses as disengagement signals, we identify at-risk customers and provide actionable strategies to shift from inefficient mass calling to targeted retention efforts.

---
## 🪜Project Workflow

|Stage (Notebook)              | Description                        |
|------------------------------|------------------------------------|
| P1 - S1 Data Wrangling       | Preprocessing Steps                |
| P1 - S2 Data Modeling        | Pipeline Construction & Validation |
| P1 - S3 Data Visualization   | Signal Detection & Validation      |

---
## 👥Business Impact

Model achieves 89.1% accuracy and 49.5% precision when targeting top 10% highest-probability customers (vs. 11.3% baseline conversion).

---
## 🛑Critical Risk Zone

Middle-aged customers (30-50) with calls <200 seconds during unfavorable economic conditions.

---
## 🔑Key Findings

Top 10 Churn Drivers:

  1. duration (call length - #1 predictor)
  2. euribor3m (economic rates)
  3. age
  4. nr.employed
  5. campaign (contact frequency)
  6. pdays_never_contacted
  7. emp.var.rate
  8. cons.price.idx
  9. cons.conf.idx
  10. pdays
---
## 🔨Technical Stack
    Core: pandas, scikit-learn, matplotlib, seaborn
    Imbalance Handling: imblearn (SMOTE)
    Preprocessing: ColumnTransformer, StandardScaler, OneHotEncoder
    Models: LogisticRegression, RandomForestClassifier
    Evaluation: ROC-AUC, Precision-Recall curves, confusion matrices
---
## ⚖️Ethical Considerations
- Anonymized data only (no PII)
- GDPR-compliant contact limits (max 3 calls)
- Transparent feature importance (no black box)
- No demographic discrimination
- Easy opt-out mechanisms required for deployment

