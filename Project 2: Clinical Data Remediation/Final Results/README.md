# 🏦BUSINESS PROPOSAL: PREDICTIVE ENGAGEMENT MODELING FOR RETAIL BANKING

- Prepared by: Christian Shannon, Ashley Love, Mugtaba Awad, and Kirsten Livingston
  Bellevue University
  DSC 450-T201 Applied Data Science
  Professor Fadi Alsaleem
  February 13, 2026
---

| **Project Deliverables & Repository Access** | **Links**|
|--------------------------------------------|--|
| **GitHub Repository:** | https://github.com/pandakitty/Diabetes_Clinical_Remediation_Pipeline <br> *(Contains Jupyter Notebooks, datasets, and end-to-end development)* |
| **Recorded Presentation (MP4):** | https://github.com/pandakitty/Diabetes_Clinical_Remediation_Pipeline/blob/main/Final_Project_Presentation.mp4 <br> *(Full Recorded Video Presentation for Project 2)* |
| **Milestone 1:** | https://github.com/pandakitty/Diabetes_Clinical_Remediation_Pipeline/blob/main/documentation/Project_Proposal_and_Clinical_Framework.pdf <br> *(Project Proposal & Framework: Established the DQI baseline and identified clinical domain constraints.)* |
| **Milestone 2:** | https://github.com/pandakitty/Diabetes_Clinical_Remediation_Pipeline/blob/main/documentation/Technical_Design_and_Progress_Report.pdf <br> *(Technical Design & Progress: Developed core Python modules and executed initial MICE/RE logic tests.)* |
| **Milestone 3:** | https://github.com/pandakitty/Diabetes_Clinical_Remediation_Pipeline/blob/main/documentation/Final_Technical_White_Paper.pdf <br> *(Final Technical White Paper: Final forensic audit, KDE validation, and strategic clinical roadmap.)* |
- Executive Summary This report details the implementation of a Python-based Clinical Data Quality Pipeline designed to remediate systemic defects in the Diabetes 130-US Hospitals dataset. Clinical data often suffer from significant missingness and a lack of standardization, which compromises downstream predictive modeling. By utilizing a modular technical stack including Scikit-Learn’s ITERATIVE IMPUTER and Python’s Regular Expression (RE) library, the team achieved a 25% increase in the Data Quality Index (DQI). This project demonstrates a scalable framework for converting raw clinical “noise” into high-fidelity data assets.  
---

## ✋INTRODUCTION
In healthcare informatics, data integrity is a prerequisite for patient safety and hospital efficiency. The Diabetes 130-US Hospitals dataset, representing a decade of clinical care, contains significant “noise”, specifically non-standardized medical codes and missing demographic markers (Strack et al., 2024). The team hypothesized that a modular, automated remediation pipeline would outperform traditional manual cleaning by providing a statistically sound, reproducible method for handling missingness. The primary objective was to improve the DQI –encompassing completeness, validity, and consistency. Thereby creating a reliable asset for predicting hospital readmission (Pipino et al., 2002). 

---
## 📋METHODS/ANALYSIS
The project was executed through a structured Software Development Lifecycle (SDLC) involving three core technical roles

**🤹Phase 1: Clinical Audit and Wrangling**
The Data Wrangler initiated a quantitative audit using Pandas and NumPy. Initial findings revealed that 97% of the weight data was missing. Because simple deletion would result in a significant loss of statistical power, the team identified “sentinel” null values (placeholders such as “?”) for target remediation (Pipino et al., 2002). 
 
**⏱️Phase 2: Advanced Remediation**
The Data Scientist implemented Multivariate Imputation by Chained Equations (MICE) via the Scikit-Learn Iterative Imputer. MICE was selected because it models each missing variable as a function of the others, thereby preserving the relationships within the 101,766 patient encounters (Azur et al., 2011). Simultaneously, Regular Expressions were used to normalize ICD-9 medical codes, ensuring consistency across disparate hospital records. 

**📊Phase 3: Visual Validation**
To ensure the input remained medically plausible, the Data Visualizer utilized Kernel Density Estimate (KDE) plots. These “before-and-after” visualizations confirmed that the statistical distribution of variables like “time in hospital” and “medication count” remained consistent post-remediation, validating the fidelity of the MICE algorithm (Waskom, 2021). 

---
## 🟰RESULTS
The pipeline achieved the target 25% improvement in DQI. The final Exploratory Data Analysis (EDA) revealed an 11.2% readmission rate, with high-risk concentrations among geriatric patients. We recommended that clinical stakeholders adopt this modular framework to combat “data decay” and ensure that predictive models are built on standardized, complete records. 

## 🏁CLINICAL IMPLEMENTATION & SUSTAINABILITY
To transition from this successful pilot to a sustained clinical standard, we recommend that the organization adopt this modular pipeline as a foundational layer for all future predictive analytics. By integrating the Sentinel Unmasking logic directly into the hospital’s data-entry gateways, leadership can proactively combat “data decay” before it enters the longitudinal record. Furthermore, because this framework is department-agnostic, we suggest scaling these remediation protocols to Cardiology and Oncology departments to standardize hospital-wide metrics. Ultimately, this pipeline serves more than a data-cleaning tool; it provides the high-fidelity foundation required to build real-time clinical decision support systems that can accurately flag the 11.2% readmission cohort for preventative intervention.

---
## ⁉️APPENDIX
**Part A: Discovery Questions (Investigation Questions)**
Q1: Who are the primary stakeholders for this pipeline? A: Clinical administrators, hospital data scientists, and preventative care teams focused on reducing readmission rates.

Q2: What was the primary "remedy" applied to the data? A: A combination of Multivariate Imputation by Chained Equations (MICE) for missingness and Regular Expression (RE) patterns for clinical code normalization.

Q3: Why was MICE chosen over simple mean/median imputation? A: Clinical markers are interdependent. MICE preserves these relationships (e.g., correlation between weight and lab results), whereas mean imputation flattens variance and introduces bias.

Q4: How did the team handle the 97% missingness in patient weight? A: Rather than deleting the records, we used auxiliary variables (gender, age, and diagnoses) to impute weight values, maintaining the full sample size of 101,766 encounters.

Q5: How does the pipeline handle the high concentration of elderly patients? A: The logic accounts for age-related skews by using “medication counts” and “time in hospital” as key predictors to ensure imputed data reflects geriatric clinical patterns.

Q6: How do DQI dimensions (Completeness, Validity, Consistency) correlate with patient safety? A: High-fidelity data ensures clinical decision support systems are not making recommendations based on "hallucinated" or fragmented data, reducing medical error risks.

Q7: How did the team ensure remediation didn't introduce "data drift"? A: We used Kernel Density Estimate (KDE) plots to overlay pre- and post-remediation distributions. The identical "shape" of the data proved statistical fidelity was maintained.

Q8: What was the primary obstacle in the Data Acquisition phase? A: "Sentinel Unmasking"—identifying that characters like "?" were not actual data but placeholders for null values, requiring a manual clinical audit before automation.

Q9: Is the remediation pipeline department-specific? A: No. The architecture is department-agnostic and can be scaled to Cardiology or Oncology by updating the feature constraints in the DataAuditor class.

Q10: How does this project demonstrate "Role Playing Variety"? A: Per the DSC450 handout, our team rotated roles for this milestone (Project Manager, Wrangler, Scientist, Visualizer) to demonstrate cross-functional mastery of the data science process

**Part B: Stakeholder Q&A (Presentation Deliverable)**
How are the “sentinel” data identified without losing valuable clinical context? 

A: Placeholder characters like “?” are converted to standard null types before processing to ensure no medical information is deleted. 
Why was statistical imputation (MICE) chosen over simply removing incomplete records? 

A: Deleting records with missing values, such as the 97% missingness in patient weight, would have decimated the dataset. Multivariate Imputation by Chained Equations (MICE) preserves the statistical power of the 101,766 encounters by estimating values based on other clinical markers. 
How does the team ensure that “guessed” values are medically plausible?

A: The Data Visualizer performs distribution checks, such as the KDE plots in Appendix C, to ensure the “shape” of the data remains consistent. Any values falling outside of documented clinical ranges for markers like HbA1c are flagged during the audit phase. 
What significance does the 11.2% readmission rate found in the EDA have? 

A: This finding identifies the “target variable” for the project. By cleaning the data related to 11.2%, the team creates a high-fidelity asset that can eventually be used to predict which future patients are most at risk for early readmission. 
How does the pipeline handle the high concentration of elderly patients (ages 70-90)?

A: The remediation logic accounts for age-related skews in the data. Since older patients often have more complex medical histories, the pipeline uses “medication counts” and “time in hospital” as key variables to ensure the imputed data reflects geriatric clinical patterns.


---
## 📝REFERENCES
1.	Azur, M. J., Stuart, E. A., Frangakis, C., & Leaf, P. J. (2011). Multiple imputation by chained equations: What is it and how does it work? International Journal of Methods in Psychiatric Research, 20(1), 40–49.
2.	Beata, S., et al. (2014). Impact of HbA1c measurement on hospital readmission rates: Analysis of 70,000 clinical database patient records. BioMed Research International.
3.	Dua, D., & Graff, C. (2019). UCI Machine Learning Repository. University of California, Irvine.
4.	Harris, C. R., et al. (2020). Array programming with NumPy. Nature, 585(7825), 357–362.
5.	McKinney, W. (2010). Data structures for statistical computing in Python. Proceedings of the 9th Python in Science Conference.
6.	Pedregosa, F., et al. (2011). Scikit-learn: Machine learning in Python. Journal of Machine Learning Research, 12, 2825–2830.
7.	Pipino, L. L., Lee, Y. W., & Wang, R. Y. (2002). Data quality assessment. Communications of the ACM, 45(4), 211–218.
8.	Python Software Foundation. (2024). The Python Standard Library: re — Regular expression operations.
9.	Strack, B., et al. (2014). Impact of HbA1c measurement on hospital readmission rates: Analysis of 70,000 clinical database patient records. BioMed Research International.
10.	Waskom, M. L. (2021). Seaborn: Statistical data visualization. Journal of Open-Source Software, 6(60), 3021

