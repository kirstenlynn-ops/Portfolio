# BUSINESS PROPOSAL: PREDICTIVE ENGAGEMENTMODELING FOR RETAIL BANKING

- Prepared for: Stakeholders of the Bank Marketing Campaign
- Prepared by: Christian Shannon, Ashley Love, Mugtaba Awad, and Kirsten Livingston
  Bellevue University
  DSC 450-T201 Applied Data Science
  Professor Fadi Alsaleem
  January 18, 2026
---

|**Project Deliverables & Repository Access**                                       |
|-----------------------------------------------------------------------------------|
|**GitHub Repository:** https://github.com/cashannon/DSC-450-Applied-Data-Science   |
|(Contains source code, Jupiter Notebooks, and the bank-additional-full.csv dataset)|
|**Recorded Presentation:**                                                         |
|https://www.canva.com/design/DAG9koWKaK4/vhbgQZ2pM8lB56cZI8DwKg/edit               |
|(Final presentation deliverable as outlined in Part B of the Appendix)             |
- Executive Summary This proposal outlines a predictive framework to move from mass-outreach to targeted
engagement. By identifying a “Risk Zone” in the middle-aged demographic, we achieved a 49.5 % precision
rate, providing a scalable ROI-driven solution for retail banking.
---

## INTRODUCTION
In the modern retail banking landscape, the cost of acquiring new customers often exceeds the cost of retaining
existing ones. This project utilizes the “Bank Marketing” dataset (‘bank-additional-full.csv’) from a Portuguese
banking institution to investigate customer engagement patterns during term‑deposit telemarketing campaigns.
While the original objective was to predict which clients would subscribe to a term deposit after phone contact,
this work reframes the problem as a propensity‑to‑engage study. By analyzing socio‑demographic, behavioral,
and macroeconomic variables, the goal is to shift from inefficient mass calling to a data‑driven predictive
targeting approach. (Moro et al., 2014).

## BUSINESS PROBLEM/HYPOTHESIS
The core business problem is the low effectiveness of current outbound term-deposit campaigns, where
approximately 88% of contacted clients do not subscribe. This high “no” rate drives substantial operational cost
per successful conversion and increases the risk of customer fatigue –defined here as “engagement churn”. Our
hypothesis is that by identifying a specific “risk zone” of low-engagement profiles, the bank can optimize
outreach frequency and timing to improve ROI.

---
## METHODS/ANALYSIS
Our methodology followed a specialized pipeline divided into three critical roles to ensure a rigorous and
repeatable process (McKinney, 2022).
**Data Wrangling (Step-by-Step Preprocessing):**
• Structure & Imbalance: We loaded the bank-additional-full.csv file with an explicit semicolon separator
to parse all 21 original columns. We performed a deep inspection of structure and types, confirming the
absence of null values while identifying a significant class imbalance (88.7% “no” vs. 11.3% “yes”).
• Cleaned Contact History: Created a new binary indicator (pdays_never_contacted) for clients never
previously reached and recoded the placeholder value 999 to 1 to align with original documentation
conventions.
• Managed Categorical Noise: Profiling revealed “unknown” values in features like job and education;
these were retained as explicit categories to preserve potential signal rather than being imputed or
dropped.
• Feature Expansion: Utilized a OneHotEncoder on all categorical predictors, dropping the first category to
avoid the “dummy variable trap.” This expanded our feature space from 21 to 54 fully numeric columns
suitable for machine learning algorithms.

**Data Modeling (Pipeline Construction & Validation):**
The modeling workflow framed the task as a binary classification problem using a stratified training and test split (80/20) to maintain the original class imbalance. To ensure model integrity and predictive power, we
implemented the following.
• Leakage Prevention: The ‘duration’ variable was explicitly excluded prior to model training, as it is only
known after a call concludes.
• Class Balancing : We applied Synthetic Minority Over-Sampling Technique (SMOTE) strictly to the
training data to address skewed classes without leaking information into the test set.
• Model Comparison: We trained a Random Forest Classifier and a Logistic Regression baseline, evaluating
5
them on ROC- AUC and precision-recall curves (GeeksforGeeks, 2025).

**Data Visualization(Signal Detection & Validation):**
The visualization step focused on turning raw data into clear signals for disengagement and “churn” risk. We
utilized several advanced plotting techniques to validate our statistical findings.
• Density Mapping: We generated KDE heatmaps and hexbin plots of age vs. duration to identify a dense
“Risk Zone” among middle-aged clients (30-50) with short conversations.
• Distribution Analysis: Normalized bar charts compared subscription outcomes across education levels,
while boxplots of call duration by outcome highlighted “soft churn” patterns.
• Economic Correlation: We utilized KDE plots for macroeconomic indicators (like euribor3m) and a
numeric correlation heatmap to visualize how external economic factors influenced customer
engagement.
• Feature Priority: A final feature-importance bar chart was extracted from the Random Forest model to
confirm that behavioral attributes, especially contact frequency, were the strongest drivers of churn.

---
## RESULTS
The analysis revealed that targeting the top 10% highest probability customers yielded a precision of 49.5%,
nearly five times the baseline rate.
• Model Performance: The Random Forest with SMOTE achieved 89.1% accuracy and a 78.3% ROC-AUC.
Targeting the top 10% highest-probability customers yielded a precision of 49.5%.
• Primary Drivers: Feature importance pinpointed call duration as the dominant driver, followed by
economic indicators like the Euribor 3-month rate.
• The Fatigue Point: Subscription rates drop sharply after 3-4 campaign contacts, marking a threshold for
customer fatigue.

---
## CONCLUSION
This project successfully transformed the Bank Marketing dataset from a telemarketing conversion challenge
into a comprehensive customer engagement and churn prevention framework. By leveraging an optimized
Random Forest classifier, we achieved a high-performance benchmark of 89.1% model accuracy. More
importantly for the bank’s bottom line, the model reached 49.5% precision when targeting the top 10% highest-
probability customers –surpassing the baseline 11% subscription rate by nearly five-fold. This shift from
“volume-based” to a “value-based” strategy directly addresses the operational inefficiencies identified at the
project’s outset.
Key discoveries from our visual and predictive analytics revealed that low call duration (under 200 seconds)
among middle-aged clients (ages 30-50) constitutes the primary “risk zone” for disengagement. This “soft churn”
is further amplified by unfavorable economic conditions, specifically high ‘euribor3m’ interest rates, which serve
as a critical external trigger for customer withdrawal. Furthermore, our analysis established a clear “fatigue
threshold,” showing that subscription rates plummet after just three campaign contacts.
By shifting from inefficient mass calling to targeted outreach that prioritizes high-propensity profiles during
optimal outreach months, the bank can dramatically improve ROI. This strategy is not only more profitable but
more sustainable; it respects ethical boundaries through transparent modeling, robust consent protocols, and
strict contact limits that prevent customer fatigue. The integrated data wrangling pipeline, the multi-panel
visualization dashboard, and the predictive analytics framework provide a scalable, end-to-end plan for data-
driven customer experience, ensuring that the bank remains competitive in a volatile economic landscape.
