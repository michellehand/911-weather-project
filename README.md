# 911 Weather Prediction Project

## Overview

This project analyzes relationships between weather conditions and traffic-related 911 emergency call volume in Seattle. The goal was to evaluate whether meteorological conditions such as temperature, precipitation, snowfall, and severe weather events could improve prediction of traffic-related emergency demand.

The project combines historical Seattle 911 dispatch data with historical weather observations to:

- Identify operational and environmental patterns associated with traffic-related emergency calls
- Explore temporal and seasonal traffic behavior
- Build predictive machine learning models for daily traffic call volume
- Investigate anomalous traffic-call spikes
- Demonstrate end-to-end analytics and machine learning workflows using real-world public datasets

---

# Business Problem

Emergency services experience fluctuating operational demand depending on traffic behavior, seasonal activity, and environmental conditions. Better forecasting could help:

- Improve staffing allocation
- Anticipate high-demand periods
- Support emergency preparedness planning
- Reduce operational strain during abnormal traffic conditions
- Improve situational awareness for city operations

---

# Project Objectives

## Phase 1 — Data Collection & Exploration

- Acquire public 911 dispatch and weather datasets
- Clean and validate raw operational data
- Explore traffic-related emergency call behavior
- Investigate temporal and seasonal trends
- Identify anomalies and operational spikes

## Phase 2 — Feature Engineering & Modeling

- Engineer temporal and environmental forecasting features
- Build baseline regression models
- Compare machine learning approaches
- Evaluate predictive performance
- Interpret operational drivers of traffic demand

## Phase 3 — Portfolio & Reporting

- Create polished visualizations
- Summarize operational findings
- Publish portfolio-ready analytics project

---

# Dataset Sources

## Seattle 911 Dispatch Data

Public emergency dispatch records containing:

- event timestamps
- response categories
- final call types
- dispatch metadata
- operational event classifications

Traffic-related calls were isolated using the Event Group field.

## Historical Weather Data

Historical daily weather observations including:

- average temperature
- maximum temperature
- minimum temperature
- precipitation totals
- snowfall totals
- precipitation duration
- wind speed and gusts

---

# Methodology

The project followed a full analytics and machine learning workflow:

1. Data Cleaning and Validation
2. Weather and Emergency Data Integration
3. Exploratory Data Analysis
4. Feature Engineering
5. Machine Learning Modeling
6. Model Evaluation and Interpretation
7. Operational Anomaly Investigation

Traffic-related emergency calls were aggregated to the daily level and merged with historical weather observations to create a forecasting dataset.

---

# Exploratory Analysis

Initial exploratory analysis investigated:

- traffic call trends over time
- precipitation relationships
- temperature relationships
- weekday effects
- seasonal effects
- operational anomalies

Several exploratory visualizations showed:

- strong weekday traffic patterns
- meaningful seasonal variation
- weak simple linear relationships between precipitation and traffic calls
- substantial operational variability across days

---

# Operational Anomaly Investigation

Several unusually high traffic-call days were identified during June 2025.

Initial investigation suggested possible weather-related spikes. However, deeper decomposition of event categories revealed that these spikes were driven primarily by:

- TRAFFIC - MOVING VIOLATION events

rather than:

- collision-related incidents
- roadway hazards
- weather emergencies

This suggested that operational or enforcement-related activity likely contributed more strongly to these anomalies than environmental conditions alone.

---

# Feature Engineering

Engineered features included:

## Temporal Features

- weekday indicators
- weekend flags
- monthly indicators
- seasonal classifications

## Weather Features

- precipitation totals
- rain-day indicators
- heavy-rain indicators
- temperature buckets
- freezing-day indicators
- hot-day indicators

## Forecasting Features

- lagged traffic-call variables
- rolling 7-day traffic averages
- lagged precipitation variables

Lag features and rolling averages substantially improved forecasting performance by capturing temporal autocorrelation in traffic demand.

---

# Modeling Approach

Several regression models were tested:

1. Baseline Linear Regression
2. Weather-Enhanced Linear Regression
3. Random Forest Regressor
4. Random Forest with Lag Features

The primary modeling objective was:

> Determine whether weather variables improve prediction of traffic-related emergency demand beyond normal temporal traffic patterns.

---

# Modeling Results

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Baseline Linear | 30.41 | 38.52 | 0.085 |
| Weather Linear | 30.03 | 37.96 | 0.111 |
| Random Forest | 29.17 | 37.40 | 0.137 |
| Random Forest + Lag Features | 21.08 | 27.50 | 0.534 |

---

# Key Findings

## 1. Weather Provided Modest Predictive Value

Weather variables improved forecasting performance modestly beyond baseline temporal features.

This suggests that environmental conditions contribute predictive signal, but are not the dominant driver of daily traffic-related emergency demand.

## 2. Historical Traffic Behavior Was Highly Predictive

Lagged traffic-call variables dramatically improved model performance.

This indicates that traffic systems exhibit strong temporal autocorrelation:

- busy traffic days tend to cluster
- operational demand follows recurring behavioral patterns
- recent traffic activity strongly predicts near-term future activity

## 3. Random Forest Models Outperformed Linear Regression

Tree-based models significantly outperformed linear regression models, suggesting that:

- traffic systems contain nonlinear relationships
- operational behavior changes under varying environmental conditions
- temporal and environmental interactions are complex

## 4. Temperature Variables Were More Useful Than Binary Weather Flags

Continuous temperature measurements contributed substantially more predictive value than simple binary weather indicators such as:

- rain_day
- freezing_day
- hot_day

This suggests that gradual environmental variation matters more than simplified threshold-based conditions.

---

# Feature Importance Insights

The strongest predictive features included:

- lagged traffic-call volume
- rolling traffic averages
- temperature variables
- weekday patterns

Weather variables such as precipitation contributed moderate predictive signal, while binary weather flags contributed relatively little.

---

# Technical Skills Demonstrated

This project demonstrates:

- Python data analysis
- pandas data manipulation
- exploratory data analysis
- feature engineering
- machine learning modeling
- Random Forest regression
- operational analytics
- anomaly investigation
- model evaluation
- data visualization
- forecasting workflows
- real-world data cleaning

---

# Tools & Libraries

- Python
- pandas
- NumPy
- scikit-learn
- matplotlib
- Jupyter Notebook

---

# Project Structure

```text
911-weather-project/
│
├── data/
├── notebooks/
├── outputs/
├── README.md
├── requirements.txt
└── .gitignore
```

---

# Future Improvements

Potential future enhancements include:

- incorporating holiday and event calendars
- integrating traffic volume datasets
- adding roadway construction data
- experimenting with time-series forecasting models
- building interactive dashboards
- integrating real-time weather APIs
- testing advanced ensemble forecasting methods

---

# Final Conclusion

This project evolved from a simple weather-correlation investigation into a broader operational forecasting and traffic-demand analysis.

While weather conditions contributed modest predictive value, the strongest forecasting signal came from historical traffic behavior and recurring temporal patterns.

The project demonstrates how real-world operational systems are driven by a combination of:

- environmental conditions
- human behavioral patterns
- temporal structure
- operational dynamics

rather than any single isolated factor.
