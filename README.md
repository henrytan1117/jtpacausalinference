# Causal Inference: Evaluating the JTPA Job Training Program
An End-to-End Policy Evaluation using Doubly Robust ML Estimators


## Problem Statement
Despite billions of dollars in federal investment, youth unemployment and wage stagnation remain critical issues in the U.S. labor market. This project evaluates the Job Training Partnership Act (JTPA) to determine its causal impact on workers' earnings 30 months post-program.

The core challenge in this analysis is selection bias: individuals who participate in training often differ fundamentally (in motivation or background) from those who don't. This project addresses that by treating eligibility as a randomized instrument and utilizing advanced econometrics to estimate the true Average Treatment Effect (ATE).


## Methodology
To ensure a robust policy recommendation, the analysis followed these logical steps:

(1) Selection of Treatment: Focused on eligibility (randomly assigned) rather than participation (endogenous) to preserve the Randomized Controlled Trial (RCT) framework.

(2) Assumption Validation: Confirmed the Overlap and Unconfoundedness assumptions using propensity score distributions and covariance balancing checks.

(3) Model Selection: Moved beyond simple linear regressions to Double Debiased Machine Learning (DDML) to handle high-dimensional covariates and potential non-linearities.

In particular:
- Identification Strategy: Doubly Robust Estimation (combining Outcome Regression and Propensity Scores).
- Machine Learning: Lasso, Random Forest, Decision Trees, and Neural Networks for nuisance parameter estimation.
- Techniques: 3-fold cross-fitting and sample splitting to eliminate over-fitting bias.
- Subgroup Analysis: Conditional Average Treatment Effect (CATE) analysis across 12 unique demographic clusters.


## Dataset Overview
The dataset originates from the National JTPA Study (1987-1989), covering 20+ covariates including:
- Demographics: Gender, age, race, marital status.
- Pre-treatment History: Previous annual earnings, hours worked per week, education level.
- Outcome (Y): Total earnings 30 months post-assignment.


## Results & Key Findings
(1) Main Result: The estimated ATE for program eligibility is $1,324.04.

(2) Net Social Impact: After accounting for the $774 service cost per assignment, the program yields a net positive return of ~$550 per person.

(3) Best Performing Model: Lasso provided the most stable estimates with the lowest Standard Error (357.12).

(4) Heterogeneity: Subgroup analysis revealed that the program is most effective for individuals with exactly 12 years of education who were working full-time (35-40 hours) prior to the program (Net ATE: $1,771.97).


## Discussion & Policy Implications
While the program is generally effective, it is not a "one-size-fits-all" solution.

- Negative Returns: Certain subgroups, specifically unemployed individuals with more than 12 years of education, showed a negative net ATE (-$5,821.09). This suggests the program may lead to "occupational downgrading" or missed opportunity costs for higher-educated workers.
- Policy Recommendation: Targeted implementation is key. Resources should be shifted away from high-education subgroups toward mid-education, full-time workers where the ROI is highest.


## Resources
(1) jtpa.csv: The original JTPA dataset that was used in this study and analysis
(2) jtpa_report.pdf & jtpa_report.md: The full academic report of the study
(3) jtpa_slides.pdf: A summarized version of the full academic report, used for presentation and sharing session
(4) jtpa_code.rmd: The RMD R file containing the codes used to replicate the results

