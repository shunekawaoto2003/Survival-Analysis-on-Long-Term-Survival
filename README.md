# Survival Analysis on Long-Term Survival Following Hospitalization for an Acute Myocardial Infarction

This project analyzes long-term survival data from the Worcester Heart Attack Study (WHAS) for patients who have been hospitalized for an acute myocardial infarction (AMI). The goal is to identify key clinical and demographic factors that influence patient survival.

## Key Findings

The analysis, which used both Cox proportional hazards and accelerated failure time (AFT) models, found that the following variables are significant predictors of long-term survival:

* **Age**: Each additional year of age was associated with a 3.4% increase in the hazard of death and a 3.7% decrease in expected survival time.
* **Cardiogenic Shock (sho)**: Patients who experienced cardiogenic shock had a hazard 6.72 times greater than those who did not. The AFT model showed that shock patients survived only 35.1% as long as those without shock.
* **Congestive Heart Failure (chf)**: The presence of CHF was linked to an 82.5% higher risk of death at any point in time. The corresponding time ratio of 0.597 suggests a 40.3% reduction in survival time for CHF patients.

## Methodology

1.  **Data Pre-processing**: The WHAS dataset, which includes demographic, clinical, and follow-up data, was pre-processed. Continuous variables like age and creatine phosphokinase (cpk) were converted into discrete categories to improve model interpretability.
2.  **Exploratory Analysis**: Histograms and frequency tables were used to examine the distribution of variables.
3.  **Variable Selection**: Individual log-rank tests were performed to identify significant univariate predictors. Variables such as `cpk` and `mitype` were excluded from further analysis because their p-values were greater than alpha =0 .05.
4.  **Cox Proportional Hazards (Cox PH) Model**:
    * Variable selection was performed using best-subset and forward stepwise selection.
    * The final model included age, cardiogenic shock (`sho`), and congestive heart failure (`chf`).
    * The proportional hazards assumption was checked using log-log survival plots, which showed that `miord` (MI order) violated this assumption and was therefore excluded.
5.  **Accelerated Failure Time (AFT) Model**:
    * Three nested distributions (Exponential, Weibull, and Generalized Gamma) were fitted to the data.
    * Likelihood ratio tests (LRTs) were used to compare the models, and the Generalized Gamma distribution was selected as the best-fitting model based on a statistically significant improvement in fit (p = 0.009). This model directly estimates how covariates affect survival time.

## Consistency of Results

Both the Cox PH and AFT models identified the same three variables (age, sho, and chf) as significant predictors of mortality. Variables associated with higher hazards in the Cox model corresponded to lower time ratios in the AFT model, providing strong and reliable evidence for the findings.
