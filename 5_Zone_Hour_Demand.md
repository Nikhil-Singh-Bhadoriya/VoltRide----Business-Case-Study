# Zone Hour Demand Analysis

## Table of Contents
1. [Overview](#overview)
2. [Dataset Description](#dataset-description)
3. [Hourly Analysis](#hourly-analysis)
4. [Zone-Hour Pattern Analysis](#zone-hour-pattern-analysis)
5. [City-wise Contribution Analysis](#city-wise-contribution-analysis)
6. [Outlier Detection](#outlier-detection)
7. [Key Insights](#key-insights)
8. [Recommendations](#recommendations)

---

## Overview

This analysis examines the **Zone Hour Demand** dataset to understand ride request and cancellation patterns across different zones, hours, and cities. The goal is to identify:
- Peak demand hours
- High cancellation periods
- Zone-specific patterns
- City-wise performance metrics
- Anomalies and outliers

---

## Dataset Description

**File:** `Zone_Hour_Demand.csv`

**Key Columns:**
- `Zone`: Geographic zone identifier (1-10)
- `City`: City name (Bengaluru, Delhi, Hyderabad, Mumbai)
- `Hour`: Hour of the day (0-23)
- `Avg_Ride_Requests`: Average number of ride requests
- `Avg_Cancellations`: Average number of ride cancellations

---

## Hourly Analysis

### Average Ride Requests by Hour

The hourly analysis reveals clear patterns in ride demand throughout the day:

| Hour | Avg Ride Requests | Avg Cancellations |
|------|-------------------|-------------------|
| 0    | 109.30           | 19.33            |
| 1    | 105.15           | 21.83            |
| 2    | 106.55           | 21.08            |
| 3    | 104.10           | 21.00            |
| 4    | 106.40           | 22.70            |
| 5    | 115.43           | 21.93            |
| 6    | 118.73           | 21.13            |
| 7    | 118.00           | 21.98            |
| 8    | 122.00           | 20.93            |
| 9    | 113.48           | 22.18            |
| 10   | 99.28            | 19.45            |
| 11   | 106.40           | 20.28            |
| 12   | 115.90           | 20.68            |
| 13   | 113.60           | 21.58            |
| 14   | 119.85           | 21.90            |
| 15   | 109.30           | 21.15            |
| 16   | 114.58           | 18.53            |
| 17   | 125.68           | 20.08            |
| 18   | 111.93           | 24.50            |
| 19   | 112.20           | 22.83            |
| 20   | 125.40           | 22.08            |
| 21   | 122.55           | 22.08            |
| 22   | 108.25           | 20.78            |
| 23   | 108.83           | 18.83            |

### Key Hourly Patterns

**Peak Demand Hours:**
- **Hour 17 (5 PM)**: 125.68 average requests - Evening rush hour
- **Hour 20 (8 PM)**: 125.40 average requests - Post-work travel
- **Hour 8 (8 AM)**: 122.00 average requests - Morning commute
- **Hour 21 (9 PM)**: 122.55 average requests - Night activity

**Low Demand Hours:**
- **Hour 10 (10 AM)**: 99.28 average requests - Mid-morning lull
- **Hour 3 (3 AM)**: 104.10 average requests - Late night

**Peak Cancellation Hours:**
- **Hour 18 (6 PM)**: 24.50 average cancellations
- **Hour 4 (4 AM)**: 22.70 average cancellations
- **Hour 19 (7 PM)**: 22.83 average cancellations

**Low Cancellation Hours:**
- **Hour 23 (11 PM)**: 18.83 average cancellations
- **Hour 16 (4 PM)**: 18.53 average cancellations
- **Hour 0 (12 AM)**: 19.33 average cancellations

---

## Zone-Hour Pattern Analysis

### Zone-wise Correlation (Requests vs Cancellations)

| Zone | Correlation Coefficient |
|------|------------------------|
| 1    | -0.040                |
| 2    | 0.150                 |
| 3    | -0.078                |
| 4    | 0.061                 |
| 5    | 0.030                 |
| 6    | -0.052                |
| 7    | -0.018                |
| 8    | -0.027                |
| 9    | 0.023                 |
| 10   | 0.190                 |

**Insights:**
- **Zone 10** shows the highest positive correlation (0.190) - higher requests lead to higher cancellations
- **Zone 2** also shows positive correlation (0.150)
- **Zone 3** shows negative correlation (-0.078) - higher requests may lead to fewer cancellations (better supply-demand balance)
- Most zones show weak correlation, suggesting cancellations are influenced by factors beyond request volume

### Peak Hours by Zone

| Zone | Peak Request Hour | Max Requests | Peak Cancellation Hour | Max Cancellations |
|------|------------------|--------------|----------------------|-------------------|
| 1    | 21 (9 PM)       | 199          | 5 (5 AM)             | 39               |
| 2    | 13 (1 PM)       | 199          | 16 (4 PM)            | 39               |
| 3    | 8 (8 AM)        | 198          | 20 (8 PM)            | 39               |
| 4    | 23 (11 PM)      | 197          | 7 (7 AM)             | 39               |
| 5    | 20 (8 PM)       | 199          | 2 (2 AM)             | 39               |
| 6    | 23 (11 PM)      | 196          | 22 (10 PM)           | 38               |
| 7    | 21 (9 PM)       | 193          | 2 (2 AM)             | 39               |
| 8    | 20 (8 PM)       | 199          | 0 (12 AM)            | 39               |
| 9    | 3 (3 AM)        | 199          | 17 (5 PM)            | 39               |
| 10   | 20 (8 PM)       | 196          | 6 (6 AM)             | 39               |

**Zone-Specific Insights:**
- **Zone 9** has an unusual peak at 3 AM, suggesting night-shift workers or entertainment districts
- **Zones 1, 5, 7, 8, 10** peak at evening hours (8-9 PM) - typical residential areas
- **Zone 2** peaks at 1 PM - business/commercial district
- **Zone 3** peaks at 8 AM - commuter zone
- Peak cancellations often don't align with peak requests, suggesting different underlying causes

### Sample Zone-Hour Data

| Zone | Hour | Avg Ride Requests | Avg Cancellations |
|------|------|-------------------|-------------------|
| 1    | 0    | 141.00           | 14.00            |
| 1    | 1    | 141.75           | 21.25            |
| 1    | 2    | 125.75           | 18.50            |
| 1    | 3    | 70.00            | 16.00            |
| 1    | 4    | 118.00           | 23.25            |
| 1    | 5    | 79.00            | 25.50            |
| 1    | 6    | 121.75           | 18.75            |
| 1    | 7    | 74.00            | 18.50            |
| 1    | 8    | 115.00           | 25.75            |
| 1    | 9    | 99.75            | 23.50            |

---

## City-wise Contribution Analysis

### Overall City Performance

| City      | Total Requests | Avg Requests | Total Cancellations | Avg Cancellations | Cancellation Rate (%) |
|-----------|----------------|--------------|---------------------|-------------------|-----------------------|
| Bengaluru | 26,636         | 110.98       | 4,990               | 20.79             | 18.73                |
| Delhi     | 26,971         | 112.38       | 5,109               | 21.29             | 18.94                |
| Hyderabad | 27,284         | 113.68       | 5,132               | 21.38             | 18.81                |
| Mumbai    | 27,623         | 115.10       | 5,119               | 21.33             | 18.53                |

### City-Specific Insights

**Mumbai:**
- ✅ Highest total ride requests (27,623)
- ✅ Highest average requests per zone-hour (115.10)
- ✅ **Lowest cancellation rate (18.53%)**
- Best performing city overall - strong demand and efficient service

**Hyderabad:**
- Total requests: 27,284 (2nd highest)
- ⚠️ Highest total cancellations (5,132)
- Cancellation rate: 18.81%
- High demand but operational challenges

**Delhi:**
- Total requests: 26,971 (3rd)
- ⚠️ **Highest cancellation rate (18.94%)**
- Average cancellations: 21.29
- Needs attention to reduce cancellation rate

**Bengaluru:**
- Lowest total requests (26,636)
- Lowest average cancellations (20.79)
- Cancellation rate: 18.73%
- Relatively balanced performance

**Overall Metrics:**
- **Average cancellation rate across all cities**: 18.75%
- **Total ride requests across all cities**: 108,514
- **Total cancellations across all cities**: 20,350

---

## Outlier Detection

Outliers were identified using the **Interquartile Range (IQR) method** with a threshold of 1.5×IQR.

### Methodology

For each zone:
1. Calculate Q1 (25th percentile) and Q3 (75th percentile) for both ride requests and cancellations
2. Calculate IQR = Q3 - Q1
3. Identify outliers:
   - Values < Q1 - 1.5×IQR (lower outliers)
   - Values > Q3 + 1.5×IQR (upper outliers)

### Outlier Characteristics

Outliers typically represent:
- **Upper outliers in requests**: Unexpected demand spikes (events, holidays, weather)
- **Lower outliers in requests**: System issues, service disruptions, or unusually low demand
- **Upper outliers in cancellations**: Driver shortages, surge pricing resistance, or system problems
- **Lower outliers in cancellations**: Excellent service matching or low demand periods

### Analysis Scope

The analysis detected outliers across all 10 zones, examining:
- 24 hours × 10 zones = 240 data points per metric
- Both ride requests and cancellation patterns
- Zone-specific anomalies and unusual patterns

---

## Key Insights

### 1. Demand Patterns

✅ **Strong Evening Peak**: Hours 17-21 (5 PM - 9 PM) see consistently high demand
- Peak at 17:00 (125.68 requests) and 20:00 (125.40 requests)

✅ **Morning Commute**: Hour 8 (8 AM) shows strong demand (122.00 requests)

⚠️ **Mid-Morning Dip**: Hour 10 (10 AM) is the lowest demand period (99.28 requests)

### 2. Cancellation Patterns

⚠️ **Critical Hour 18 (6 PM)**: Highest cancellations (24.50) during evening rush
- Likely due to driver shortages during peak demand

✅ **Night Efficiency**: Late evening (Hour 23) has lowest cancellations (18.83)

⚠️ **Early Morning Issues**: Hour 4 (4 AM) shows high cancellations (22.70)
- Low driver availability during night hours

### 3. Zone Characteristics

📍 **Zone 10**: Highest correlation (0.190) - supply-demand imbalance
📍 **Zone 9**: Unusual 3 AM peak - special use case (nightlife/shift workers)
📍 **Zones 1, 5, 7, 8, 10**: Evening peaks - residential zones
📍 **Zone 2**: Midday peak - commercial district
📍 **Zone 3**: Morning peak - commuter zone

### 4. City Performance

🏆 **Mumbai - Best Overall**:
- Highest demand (27,623 requests)
- Lowest cancellation rate (18.53%)
- Most efficient operations

⚠️ **Delhi - Needs Improvement**:
- Highest cancellation rate (18.94%)
- Operational challenges to address

📊 **Hyderabad - High Volume**:
- Second highest demand
- Highest absolute cancellations (5,132)
- Scale management needed

💡 **Bengaluru - Balanced**:
- Lowest demand but stable performance
- Room for growth

---

## Recommendations

### 1. Supply Management

**Peak Hours (17-21):**
- Increase driver incentives during evening rush (17:00-21:00)
- Pre-position drivers in high-demand zones before peak hours
- Implement dynamic pricing to balance supply-demand

**Hour 18 Critical Period:**
- **Priority action**: Deploy additional drivers at 6 PM
- Address the highest cancellation rate (24.50)
- Consider guaranteed pickup bonuses

### 2. Zone-Specific Strategies

**Zone 10 (High Correlation):**
- Improve supply-demand matching algorithms
- Increase driver availability during peak hours
- Monitor and address systematic issues

**Zone 9 (3 AM Peak):**
- Ensure night-shift driver availability
- Create specialized incentives for late-night drivers
- Partnership with entertainment venues or shift-based industries

**Commercial Zones (Zone 2):**
- Midday driver availability programs
- Business district partnerships
- Corporate booking incentives

### 3. City-Level Actions

**Delhi (Highest Cancellation Rate - 18.94%):**
- Investigate root causes of cancellations
- Driver training and engagement programs
- Improve matching algorithms
- Address driver supply issues

**Hyderabad (Highest Absolute Cancellations):**
- Scale operations efficiently
- Add driver capacity
- Optimize zone-level supply distribution

**Mumbai (Model City):**
- Document best practices
- Replicate successful strategies to other cities
- Continue optimization efforts

**Bengaluru (Growth Opportunity):**
- Marketing campaigns to increase demand
- New user acquisition programs
- Service expansion

### 4. Cancellation Reduction

**Immediate Actions:**
- Reduce Hour 18 cancellations (24.50 → target: <20)
- Address early morning cancellations (Hours 1-5)
- Target overall rate reduction from 18.75% to <15%

**Systematic Improvements:**
- Better driver-rider matching
- Improved ETA accuracy
- Driver retention programs
- Penalty system for consistent cancellations

### 5. Operational Efficiency

**Mid-Morning Optimization:**
- Hour 10 demand is lowest (99.28 requests)
- Schedule driver breaks during low-demand periods
- Maintenance windows for vehicles
- Driver training sessions

**Data-Driven Decisions:**
- Real-time monitoring dashboards
- Predictive analytics for demand forecasting
- Zone-hour level optimization
- Automated alert systems for anomalies

---

## Conclusion

The Zone Hour Demand analysis reveals clear patterns in ride-sharing behavior across zones, hours, and cities. Mumbai leads in performance with the lowest cancellation rate, while Delhi requires immediate attention to reduce its 18.94% cancellation rate. The evening peak (17:00-21:00) represents both the highest opportunity and challenge, with Hour 18 showing critical cancellation levels at 24.50.

**Priority Actions:**
1. ⚠️ Address Hour 18 cancellation crisis
2. 🎯 Replicate Mumbai's success in other cities
3. 📈 Optimize supply for evening peak hours (17-21)
4. 🔍 Investigate Zone 10's high correlation issue
5. 💡 Leverage Zone 9's unique 3 AM demand pattern

By implementing these recommendations, the platform can improve service quality, reduce cancellation rates below 15%, and increase overall customer satisfaction while optimizing driver utilization and earnings.


**Dataset**: Zone_Hour_Demand.csv  
**Total Records Analyzed**: 960 zone-hour combinations (10 zones × 24 hours × 4 cities)
