# Coupon Targeting Strategy: A/B Experiment Analysis

## Overview
A retailer A**** ran a randomized A/B experiment offering a 20% discount coupon to ~5,000 recent website visitors who hadn't purchased in the last two months. 

This project analyzes the experiment to answer a core business question: **should the coupon be sent to everyone, or only to specific customer segments, to maximize revenue?**

## Approach/Methods
- **Randomization checks**: balance tests on pre-treatment covariates and a logistic regression of treatment on covariates to confirm valid random assignment.
- **Average treatment effect (ATE)**: difference-in-means t-tests on transactions and revenue.
- **Heterogeneous treatment effects**: model-free subgroup comparisons plus OLS regressions with treatment–covariate interaction terms to identify which segments respond most to the coupon.
- **Targeting policy design and evaluation**, comparing three approaches:
  - **Option 1 - Simple rule**: target users with items in their cart and low past-purchase count.
  - **Option 2 - OLS uplift model**: individual-level treatment effect estimates from an interaction model, targeting users with positive predicted uplift.
  - **Option 3 - Two-part model**: separate models for purchase probability and conditional spend, to handle the many zero-revenue outcomes.
- **Policy evaluation**: Inverse Propensity Weighting (IPW) to estimate unbiased total/per-user revenue under each policy, with bootstrapped 95% confidence intervals.
- **Out-of-sample application**: the winning policy applied to a new pool of 6,000 next-campaign users, with projected revenue compared across all strategies.

## Key Results
- The coupon significantly increased transactions but had no significant effect on revenue overall: blanket couponing isn't profitable.
- Effects were highly heterogeneous: users with items in their cart and fewer past purchases responded far more strongly.
- **Final recommendation**: adopt the simple, transparent rule (target users with cart items + ≤2 past purchases) as the primary targeting policy. It achieves revenue gains comparable to the more complex models while targeting far fewer users (i.e. the highest revenue per coupon sent), and its logic is easy to explain and operationalize.

## Tools Used
Python (pandas, numpy, scipy, statsmodels, matplotlib, seaborn)

## Repository Contents
- Analysis notebook (data loading → randomization checks → ATE → heterogeneity → targeting policy design → IPW policy evaluation → next-campaign application)
- `data_dictionary.md`: describes all variables used in the analysis 
  
  This analysis uses real experimental data provided for academic use only, so the raw dataset is not included in this repository. The notebook is shared to demonstrate methodology
