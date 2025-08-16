# Customer Contribution Scoring (Feature Engineering Project)

## Overview

This project was created out of curiosity and eagerness to tackle a challenging problem as a beginner in data science. I wanted to build a **customer recommendation predictor**, a rare and non-trivial task, to sharpen my skills with hands-on work.  

The dataset I used was **limited and did not include a target variable (y label)**. Despite this, I managed to extract meaningful features and create a recommendation target label.

---

## Creating the Recommendation Score

Since there was no target label, I engineered a **customer recommendation score** (`RecommendPercent`) ranging from 0 to 100 using the following formula:

RecommendScore = 0.3 * SpendNorm
+ 0.25 * (1 - ReturnRate)
+ 0.2 * PremiumRatioNorm
+ 0.15 * NoReturns
+ 0.1 * (1 - NewCustomer)


Where:  

- **SpendNorm** → normalized `TotalSpent_x` (scaled 0–1)  
- **PremiumRatioNorm** → normalized `premium_item_ratio_x` (scaled 0–1)  
- **ReturnRate** → `ReturnRate_x` (0–1)  
- **NoReturns** → 0/1 feature indicating if the customer made no returns  
- **NewCustomer** → 0/1 feature, flipped so that existing customers get higher score  

Finally, the recommendation percentage is calculated as:
        `Recommend = RecommendScore * 100`

---

## Feature Engineering and Challenges

- Extracted the most meaningful features from a **limited dataset**.  
- Handled missing and inconsistent data, outliers, and rounding for better analysis.  
- Created a **target label** for further segmentation.  

This process took over a week and gave me a deep understanding of **feature engineering**, which was the main goal of the project.  

---

## Segmentation

Based on the `RecommendPercent`, customers were divided into:

- **Regular Customers** → `RecommendPercent ≥ 55%`  
- **At-risk Customers** → `RecommendPercent < 55%`  

This allows for meaningful business actions, like retention campaigns or upselling opportunities.

---

## Notes

- I did not focus on building a predictive model for this dataset, as it was not ideal for modeling.  
- The main purpose was to **practice and understand feature engineering** and customer scoring.  
- Future projects will apply these learnings to **better datasets**, allowing for actual predictive modeling.

---

## Learning Outcomes

- Hands-on experience with **feature extraction and normalization**  
- Handling **missing values, NaNs, and outliers** safely  
- Creating meaningful **business-oriented target labels** from raw data  
- Understanding how **real-world datasets often require heavy preprocessing** before modeling
