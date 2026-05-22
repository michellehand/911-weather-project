# Data Dictionary

## 911 Dispatch Dataset

| Column | Description | Type / Format | Notes |
|---|---|---|---|
| CAD Event Number | Unique identifier for each 911/CAD event | String / ID | Used to identify individual dispatch records |
| CAD Event Original Time Queued | Timestamp when the event entered the CAD system | Datetime | Used to create date, hour, weekday, month, and lag features |
| Call Type | Original call classification | Categorical | Broad intake-level call type |
| Priority | Dispatch priority level | Categorical / Numeric | Indicates urgency or response priority |
| Final Call Type | Final categorized event type after dispatch processing | Categorical | Used to investigate traffic subtypes such as moving violations |
| Dispatch Latitude | Latitude of dispatch location | Float | Used for geographic analysis if needed |
| Dispatch Longitude | Longitude of dispatch location | Float | Used for geographic analysis if needed |
| Dispatch Neighborhood | Neighborhood associated with dispatch location | Categorical | Useful for spatial grouping |
| CAD Event First Response Time (s) | Time in seconds until first response | Numeric | Could be used in future response-time analysis |
| Event Group | High-level event category | Categorical | Used to filter traffic-related calls |

---

## Weather / Daily Merged Dataset

| Column | Description | Type / Format | Notes |
|---|---|---|---|
| date | Calendar date | Date | Join key between 911 calls and weather data |
| traffic_calls | Total traffic-related 911 calls for that date | Integer | Target variable for modeling |
| time | Weather observation date/time | Date / Datetime | Source weather timestamp |
| temperature_2m_mean (°F) | Mean daily temperature | Float | Weather predictor |
| temperature_2m_min (°F) | Minimum daily temperature | Float | Weather predictor |
| temperature_2m_max (°F) | Maximum daily temperature | Float | Weather predictor |
| precipitation_sum (inch) | Total daily precipitation | Float | Weather predictor |
| rain_sum (inch) | Total daily rainfall | Float | Used to evaluate rain-specific effects |
| snowfall_sum (inch) | Total daily snowfall | Float | Used to evaluate winter weather effects |
| precipitation_hours (h) | Number of hours with precipitation | Float | Measures precipitation duration |
| wind_speed_10m_max (mp/h) | Maximum daily wind speed | Float | Weather predictor |
| wind_gusts_10m_max (mp/h) | Maximum daily wind gust | Float | Weather predictor |

---

## Engineered Features Dataset

| Column | Description | Type / Format | Notes |
|---|---|---|---|
| date | Calendar date | Date | Primary time index |
| traffic_calls | Total traffic-related 911 calls | Integer | Modeling target |
| time | Weather observation date/time | Date / Datetime | Original weather timestamp |
| temperature_2m_mean (°F) | Mean daily temperature | Float | Raw weather feature |
| temperature_2m_min (°F) | Minimum daily temperature | Float | Raw weather feature |
| temperature_2m_max (°F) | Maximum daily temperature | Float | Raw weather feature |
| precipitation_sum (inch) | Total daily precipitation | Float | Raw weather feature |
| rain_sum (inch) | Total daily rainfall | Float | Raw weather feature |
| snowfall_sum (inch) | Total daily snowfall | Float | Raw weather feature |
| precipitation_hours (h) | Number of precipitation hours | Float | Raw weather feature |
| wind_speed_10m_max (mp/h) | Maximum wind speed | Float | Raw weather feature |
| wind_gusts_10m_max (mp/h) | Maximum wind gust | Float | Raw weather feature |
| year | Year extracted from date | Integer | Calendar feature |
| month | Month extracted from date | Integer | Seasonal feature |
| day_of_week | Name of weekday | Categorical | Example: Monday, Tuesday |
| day_of_week_num | Numeric weekday | Integer | Monday = 0, Sunday = 6 |
| weekend | Indicates Saturday or Sunday | Boolean / Binary | 1 if weekend, 0 otherwise |
| season | Season derived from month | Categorical | Winter, Spring, Summer, Fall |
| rain_day | Indicates whether precipitation occurred | Boolean / Binary | True if precipitation > 0 |
| precip_bucket | Precipitation intensity category | Categorical | No Rain, Light Rain, Moderate Rain, Heavy Rain |
| temp_bucket | Temperature category | Categorical | Freezing, Cold, Mild, Warm |
| freezing_day | Indicates freezing conditions | Boolean / Binary | True if min temperature ≤ 32°F |
| hot_day | Indicates hot conditions | Boolean / Binary | True if max temperature met hot-day threshold |
| heavy_rain_day | Indicates heavy precipitation | Boolean / Binary | True if precipitation met heavy-rain threshold |
| traffic_calls_lag_1 | Previous day’s traffic call volume | Numeric | Captures short-term traffic memory |
| precipitation_lag_1 | Previous day’s precipitation | Numeric | Captures delayed weather effects |
| temperature_max_lag_1 | Previous day’s maximum temperature | Numeric | Captures delayed temperature effects |
| traffic_calls_7_day_avg | Rolling 7-day average traffic calls | Numeric | Captures recent traffic trend |
| precipitation_3_day_total | Rolling 3-day precipitation total | Numeric | Captures accumulated precipitation effects |
