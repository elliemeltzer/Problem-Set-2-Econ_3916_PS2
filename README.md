# PS2 - The Survey That Wasn't Random

## Overview

This project examines how nonresponse bias can make a survey result look convincing even when it does not represent the full population. A simulated product survey appears to show that satisfaction increased substantially after an onboarding redesign, but the apparent improvement is mostly caused by a change in who answered the survey.

## Methods

- Simulated 50,000 users before and after the redesign
- Created engagement and support-ticket variables related to satisfaction
- Modeled selective survey response using a logistic function
- Built percentile and BCa bootstrap confidence intervals
- Evaluated interval coverage with a Monte Carlo simulation
- Conducted a two-sample test and power analysis
- Tested whether larger samples reduce response bias
- Attempted inverse-probability weighting using observed user characteristics

## Key Findings

The true population mean increased by only about **0.10 points**, from approximately **3.30 to 3.40**. However, the observed respondent mean increased from about **3.60 to 4.30** because satisfied users became much more likely to respond after the redesign.

The post-redesign respondent mean had a narrow 95% bootstrap interval of approximately **4.29 to 4.32**, but this precision did not correct the survey’s selection bias. Increasing the sample size reduced variability while leaving the estimate roughly **0.92 points above the true mean**.

Inverse-probability weighting reduced the post-redesign estimate from approximately **4.30 to 4.14**, but it still failed to recover the true mean of about **3.39**. The response mechanism depended directly on satisfaction, which was unavailable for nonrespondents.

## Conclusion

A large sample and a small p-value do not guarantee a representative result. When survey participation depends on the outcome being measured, additional responses can make a biased estimate more precise without making it more accurate. A better approach would randomly select users and actively follow up with the selected sample regardless of satisfaction.

## Tools

Python, NumPy, pandas, SciPy, scikit-learn, statsmodels, Matplotlib, and Google Colab.
