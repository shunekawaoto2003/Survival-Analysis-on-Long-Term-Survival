# Survival Analysis on Long-Term Survival Following Hospitalization for an Acute Myocardial Infarction

[cite_start]This project analyzes long-term survival data from the Worcester Heart Attack Study (WHAS) for patients who have been hospitalized for an acute myocardial infarction (AMI). [cite_start]The goal is to identify key clinical and demographic factors that influence patient survival[cite: 12].

## Key Findings

[cite_start]The analysis, which used both Cox proportional hazards and accelerated failure time (AFT) models, found that the following variables are significant predictors of long-term survival[cite: 8, 138]:

* [cite_start]**Age**: Each additional year of age was associated with a 3.4% increase in the hazard of death and a 3.7% decrease in expected survival time[cite: 125].
* [cite_start]**Cardiogenic Shock (sho)**: Patients who experienced cardiogenic shock had a hazard 6.72 times greater than those who did not[cite: 127]. [cite_start]The AFT model showed that shock patients survived only 35.1% as long as those without shock[cite: 128].
* [cite_start]**Congestive Heart Failure (chf)**: The presence of CHF was linked to an 82.5% higher risk of death at any point in time[cite: 129]. [cite_start]The corresponding time ratio of 0.597 suggests a 40.3% reduction in survival time for CHF patients[cite: 132].

## Methodology

1.  [cite_start]**Data Pre-processing**: The WHAS dataset, which includes demographic, clinical, and follow-up data, was pre-processed[cite: 17]. [cite_start]Continuous variables like age and creatine phosphokinase (cpk) were converted into discrete categories to improve model interpretability[cite: 22].
2.  [cite_start]**Exploratory Analysis**: Histograms and frequency tables were used to examine the distribution of variables[cite: 19, 21].
3.  [cite_start]**Variable Selection**: Individual log-rank tests were performed to identify significant univariate predictors[cite: 35]. [cite_start]Variables such as `cpk` and `mitype` were excluded from further analysis because their p-values were greater than `$\alpha=0.05$`[cite: 41].
4.  **Cox Proportional Hazards (Cox PH) Model**:
    * [cite_start]Variable selection was performed using best-subset and forward stepwise selection[cite: 72, 73].
    * [cite_start]The final model included age, cardiogenic shock (`sho`), and congestive heart failure (`chf`)[cite: 74].
    * [cite_start]The proportional hazards assumption was checked using log-log survival plots, which showed that `miord` (MI order) violated this assumption and was therefore excluded[cite: 66, 67].
5.  **Accelerated Failure Time (AFT) Model**:
    * [cite_start]Three nested distributions (Exponential, Weibull, and Generalized Gamma) were fitted to the data[cite: 90, 91, 92, 93].
    * [cite_start]Likelihood ratio tests (LRTs) were used to compare the models, and the Generalized Gamma distribution was selected as the best-fitting model based on a statistically significant improvement in fit (p = 0.009)[cite: 94, 105, 106]. [cite_start]This model directly estimates how covariates affect survival time[cite: 89].

## Consistency of Results

[cite_start]Both the Cox PH and AFT models identified the same three variables (age, sho, and chf) as significant predictors of mortality[cite: 138]. [cite_start]Variables associated with higher hazards in the Cox model corresponded to lower time ratios in the AFT model, providing strong and reliable evidence for the findings[cite: 119, 133].
