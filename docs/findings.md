# Findings

## Initial Observations

### Overall Call Volume

- Daily Seattle 911 call volume generally ranges between approximately 1,200 and 1,900 calls per day.
- Clear weekly cyclic behavior is visible in total call volume.
- Overall call volume appears to trend slightly upward from 2024 through 2026.
- Several significant dips and spikes may correspond to holidays, severe weather, major events, or reporting anomalies.

---

## Calls by Day of Week

| Day | Observation |
|---|---|
| Monday | High call volume |
| Tuesday | Slightly elevated |
| Wednesday | Similar to Monday |
| Thursday | Stable high volume |
| Friday | Highest total call volume |
| Saturday | Noticeable decline |
| Sunday | Lowest total call volume |

### Interpretation

- Weekday activity appears to drive a significant portion of emergency calls.
- Fridays may experience elevated activity due to increased travel, nightlife, and end-of-week behavior patterns.
- Sundays consistently show lower overall emergency call demand.

---

## Top Event Groups

| Event Group | Approximate Volume |
|---|---|
| Disturbance | 161k |
| Traffic | 158k |
| Suspicious Circumstances | 155k |
| Assist Public | 105k |
| Domestic Disturbance/Violence | 72k |
| Crisis Complaint | 70k |
| Assaults | 69k |

### Initial Hypotheses

Potential weather-sensitive event groups include:

- Traffic
- Automobiles
- Assist Public
- Crisis Complaint

Potential non-weather-sensitive event groups include:

- Disturbance
- Theft
- Burglary

---

## Traffic Call Analysis

### Observations

- Traffic calls show a stronger upward trend than total calls.
- Traffic calls exhibit substantial daily volatility.
- Large spikes may correspond to storms, snow events, holidays, or major commuting disruptions.
- Traffic calls appear to be a promising prediction target for weather-based modeling.

### Potential Weather Relationships

Possible predictive variables:
- Rainfall
- Snowfall
- Temperature
- Visibility
- Wind speed

---

## Next Steps

1. Acquire historical Seattle weather data
2. Aggregate weather data to daily level
3. Merge weather data with daily traffic call volume
4. Explore correlations between weather variables and traffic incidents
5. Build baseline predictive models
6. Evaluate forecasting accuracy
