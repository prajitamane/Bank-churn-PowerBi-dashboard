# Bank Customer Churn Analysis — Power BI Dashboard

## Overview
An interactive 3-page Power BI dashboard analyzing 10,000 bank customer records 
to identify churn drivers and build a data-driven risk segmentation model.

## Business Question
Why are customers churning, and which customer segments are highest risk?

## Key Findings
- **Overall churn rate: 20.37%** — well above the 5-15% typical for retail banking.
- **Geography matters:** Germany churns at ~32%, roughly double Spain and France (~16% each).
- **Age isn't linear:** the 45-60 age band is highest risk (~50% churn), notably 
  higher than customers aged 60+.
- **Counterintuitive product finding:** customers holding 3-4 products churn at 
  80-100% — the opposite of what's typically expected, since more products usually 
  signals loyalty rather than risk.

## Risk Segmentation Model
Built a composite risk score in DAX, combining four factors — product count, age band, 
geography, and account activity status — into a single Risk Segment (Low/Medium/High) 
using `VAR`, `SWITCH`, and `CALCULATE`. The model shows strong separation: High-risk 
customers churn at ~83%, roughly 8x the rate of Low-risk customers (~12%).

## Dashboard Pages
1. **Overview** — headline KPIs (total customers, churn rate, active customers)
2. **Segment Analysis** — churn broken down by geography and age, with interactive slicers
3. **Risk Drivers** — product count and risk segment analysis, plus a live 
   "churn vs. overall average" variance measure that updates on cross-filter

## Screenshots
![Overview](overview.png)
![Segment Analysis](segment-analysis.png)
![Risk Drivers](risk-drivers.png)

## Tools Used
Power BI Desktop · Power Query (data cleaning, conditional columns) · DAX 
(CALCULATE, VAR/RETURN, SWITCH, ALL)

## What I'd Explore With More Data
With transaction-level or time-series data, I'd add time intelligence measures to 
track churn trends over time and test whether risk segment assignment predicts 
churn before it happens, rather than just correlating with it.

## Dataset
[Kaggle: Bank Customer Churn Modelling](https://www.kaggle.com/datasets/shantanudhakadd/bank-customer-churn-prediction)
