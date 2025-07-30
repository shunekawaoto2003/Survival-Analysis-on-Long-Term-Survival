# Survival Analysis on Long-Term Survival Following Hospitalization for an Acute Myocardial Infarction
This project analyzes long-term survival data from the Worcester Heart Attack Study (WHAS) for patients who have been hospitalized for an acute myocardial infarction (AMI). The goal is to identify key clinical and demographic factors that influence patient survival.

Key Findings
The analysis, using both Cox proportional hazards and accelerated failure time (AFT) models, found that the following variables are significant predictors of long-term survival:


Age: Older age is associated with a higher hazard of death and a reduction in expected survival time.


Cardiogenic Shock (sho): Patients who experienced cardiogenic shock had a significantly higher risk of death (Hazard Ratio = 6.717) and a much shorter expected survival time (Time Ratio = 0.351) compared to those without shock.


Congestive Heart Failure (CHF): The presence of CHF was linked to an 82.5% higher risk of death and a 40.3% reduction in survival time.

# Methodology

Data Pre-processing: The WHAS dataset, which includes demographic, clinical, and follow-up data, was pre-processed. Continuous variables like age and creatine phosphokinase (cpk) were converted into discrete categories to improve model interpretability.


Exploratory Analysis: Histograms and frequency tables were used to examine the distribution of variables.


Variable Selection: Individual log-rank tests were performed to identify significant univariate predictors. Variables such as cpk and mitype were excluded from further analysis because they were not found to be statistically significant.

Cox Proportional Hazards (Cox PH) Model:

Variable selection was performed using best-subset and forward stepwise selection.

The final model included age, cardiogenic shock (

sho), and congestive heart failure (chf).

The proportional hazards assumption was checked using log-log survival plots, which showed that 

miord (MI order) violated this assumption and was therefore excluded.

Accelerated Failure Time (AFT) Model:

Three nested distributions (Exponential, Weibull, and Generalized Gamma) were fitted to the data.

Likelihood ratio tests (LRTs) were used to compare the models, and the Generalized Gamma distribution was selected as the best-fitting model.

This model directly estimates how covariates affect survival time.

Consistency of Results
Both the Cox PH and AFT models identified the same three variables (age, sho, and chf) as significant predictors of mortality. Variables associated with higher hazards in the Cox model corresponded to lower time ratios in the AFT model, providing strong and reliable evidence for the findings.







