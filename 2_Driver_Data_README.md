# Driver Data Analysis - Insights and Findings

## Overview
This document presents comprehensive insights from the driver data analysis, covering univariate, bivariate, and trivariate analyses to understand driver performance, behavior patterns, and key metrics across different cities.

---

## Dataset Information

### Columns Analyzed
- **Driver_ID**: Unique identifier for each driver (IDs 1 to 400)
- **City**: Geographic location of driver operations (Mumbai, Bengaluru, Delhi, Hyderabad)
- **Experience_Months**: Months of driving experience (Range: 3 to 59 months)
- **Avg_Rating**: Average driver rating (Range: 3.6 to 5.0)
- **Total_Rides_Last_30_Days**: Number of rides completed in the last month (Range: 30 to 299 rides)
- **Cancellation_Rate_%**: Percentage of rides cancelled by driver (Range: 3.09% to 19.99%)
- **Avg_Battery_Consumption_km**: Average battery consumption per kilometer (Range: 0.13 to 0.22 km)

### Dataset Size
- **Total Records**: 400 drivers
- **City Distribution**:
  - Bengaluru: 108 drivers (27%)
  - Hyderabad: 105 drivers (26.25%)
  - Delhi: 99 drivers (24.75%)
  - Mumbai: 88 drivers (22%)

---

## Key Insights

### 1. Data Quality
- **Duplicates**: No duplicate records found in the dataset
- **Missing Values**: Dataset is complete with no missing values
- All data is ready for analysis without requiring imputation

### 2. City-wise Performance Analysis

#### Cancellation Rates by City
**Key Finding**: Delhi has the highest cancellation rate, while Hyderabad has the lowest.

- **Delhi**: 12.13% (Highest cancellation rate)
- **Bengaluru**: 11.78%
- **Mumbai**: 11.59%
- **Hyderabad**: 11.54% (Lowest cancellation rate)

The differences are relatively small (0.59 percentage points between highest and lowest), suggesting consistent driver behavior across cities, though Delhi drivers show slightly higher cancellation tendency.

#### Total Rides by City (Last 30 Days)
**Key Finding**: Hyderabad leads in total rides despite having the lowest cancellation rate.

- **Hyderabad**: 17,791 rides (Highest volume)
- **Mean Experience**: 32.01 months (~2.7 years)
- **Median Experience**: 33 months
- **Range**: 3 to 59 months
- **Standard Deviation**: 16.21 months (indicating diverse experience levels)
- **Distribution**: Nearly uniform across experience ranges, slight negative skewness (-0.09)

The workforce comprises a balanced mix of junior, mid-level, and experienced drivers.

#### Experience vs Rating Relationship
**Key Finding**: Experience shows virtually no correlation with average ratings (correlation: -0.01)

This counter-intuitive finding suggests that:
- New drivers perform similarly to experienced drivers in terms of ratings
- Training effectiveness might be high, bringing new drivers up to speed quickly
- Rating is influenced by factors other than experience alone
- Service quality standards are maintained regardless of experience level
#### Experience Distribution
- Driver experience shows varied distribution across the dataset
- Range of experience levels from new drivers to highly experienced ones
- Experience metrics help understand workforce composition

#### Experience vs Rating Relationship
- Scatter plot analysis reveals correlation patterns between experience and ratings
- More experienced drivers often show different rating patterns
- Experience may be a factor in service quality

### 4. Univariate Analysis Findings

#### Statistical Distributions
For each numeric variable, the analysis revealed:

**Histograms**: Show the frequency distribution and data concentration
- Identify normal vs skewed distributions
- Reveal potential outliers and data anomalies

**Box Plots**: Highlight central tendency and spread
All numeric variables show near-normal distributions:

| Variable | Skewness | Kurtosis | Interpretation |
|----------|----------|----------|----------------|
| Experience_Months | -0.09 | -1.14 | Nearly symmetric, platykurtic |
| Avg_Rating | -0.07 | -1.13 | Nearly symmetric, platykurtic |
| Total_Rides_Last_30_Days | 0.01 | -1.22 | Perfectly symmetric, platykurtic |
| Avg_Battery_Consumption_km | -0.08 | -1.18 | Nearly symmetric, platykurtic |
| Cancellation_Rate_% | -0.07 | -1.24 | Nearly symmetric, platykurtic |

**Key Insight**: Negative kurtosis across all variables indicates flatter distributions than normal (platykurtic), suggesting data is evenly spread without extreme outliers.
**Density Plots**: Show probability distributions
**Major Finding**: All variables show weak to negligible correlations with each other.

Key correlation patterns:
- **Experience_Months vs Avg_Rating**: -0.01 (No relationship)
- **Experience_Months vs Total_Rides**: -0.05 (Very weak negative)
- **Experience_Months vs Cancellation_Rate**: 0.00 (No relationship)
- **Avg_Rating vs Total_Rides**: -0.07 (Very weak negative)
- **Avg_Rating vs Cancellation_Rate**: 0.01 (No relationship)
- **Total_Rides vs Cancellation_Rate**: 0.04 (Very weak positive)
- **Battery_Consumption vs Cancellation_Rate**: -0.05 (Very weak negative)

**Critical Insight**: The lack of strong correlations indicates that driver performance metrics operate independently. Experience doesn't predict ratings, ratings don't predict ride volumes, and cancellation rates aren't strongly tied to any single metric. This suggests multifactorial influences on driver performance.
- City distribution analyzed for frequency
- Categorical variables show clear patterns
- Helps understand geographical coverage

### 5. Bivariate Analysis Insights

#### Correlation Matrix
Comprehensive correlation analysis between all numeric variables:
- **Strong Correlations**: Identified statistically significant relationships
- **Weak Correlations**: Variables showing independence
- **Negative Correlations**: Inverse relationships between metrics

Key correlation findings:
- Experience months relationship with other performance metrics
- Battery consumption patterns vs ride frequency
- Rating correlations with cancellation rates

#### Pairplot Analysis
- Visual representation of all variable relationships
- Diagonal shows individual distributions
- Off-diagonal scatter plots reveal trends

#### Categorical vs Numeric Analysis
**Box Plots by Category**:
- Numeric variables analyzed across different cities
- Shows distribution variations by category
- Identifies city-specific patterns

**ANOVA Test Results**:
- Statistical significance tests performed
- F-statistics and p-values calculated
- Determines if categorical groupings have meaningful differences

#### Covariance Analysis
- Measures how variables change together
- Complements correlation analysis
- Provides variance information

### 6. Trivariate Analysis Findings

#### 3D Scatter Plot Insights
Multiple three-way relationships explored:

1. **Experience × Rating × Cancellation Rate**
   - Complex interactions between experience, service quality, and cancellation behavior
   - 3D patterns reveal hidden relationships not visible in 2D

2. **Total Rides × Experience × Rating**
   - Activity level interactions with experience and quality
   - Identifies high-performing driver segments
 reveal distinct patterns:

**Mumbai** (88 drivers):
- Experience vs Rating: -0.07 (weak negative)
- Experience vs Total Rides: -0.10 (weak negative)
- Battery vs Cancellation: -0.06 (weak negative)
- Most balanced correlations

**Bengaluru** (108 drivers):
- Experience vs Cancellation: 0.10 (weak positive)
- Total Rides vs Cancellation: -0.10 (weak negative)
- More experienced drivers have slightly higher cancellation rates

**Delhi** (99 drivers):
- Experience vs Battery: -0.17 (moderate negative - strongest correlation found)
- Battery vs Cancellation: -0.15 (moderate negative)
- More experienced drivers are more battery-efficient
- Better battery efficiency correlates with lower cancellations

**Hyderabad** (105 drivers):
- Total Rides vs Cancellation: 0. on Cancellation Rate**:

Drivers categorized by experience (Low/Medium/High) and rating (Low/Medium/High):

| Experience / Rating | Low Rating | Medium Rating | High Rating |
|---------------------|------------|---------------|-------------|
| **Low Experience** | 11.87% | 11.03% | 11.39% |
| **Medium Experience** | 12.86% | 12.52% | 12.02% |
| **High Experience** | 10.79% | 11.94% | 11.29% |

**Key Finding**: 
- **Best combination**: High Experience + Low Rating = 10.79% cancellation rate
- **Worst combination**: Medium Experience + Low Rating = 12.86% cancellation rate
- Medium-experienced drivers with lower ratings have the highest cancellation rates
- Highly experienced drivers maintain lower cancellation rates regardless of rating level
**Experience Level × City Performance Analysis**:

Drivers categorized as Junior (≤20 months), Mid (21-40 months), Senior (41+ months):

**Average Ratings by Experience & City** (Scale: 3.6-5.0):
- All cities maintain ratings between 4.16-4.45 across all experience levels
- Delhi consistently shows highest ratings (4.36-4.45)
- Very minimal variation by experience level within each city

**Cancellation Rates by Experience & City**:
- **Junior Drivers**: Range from 10.17% (Bengaluru) to 12.60% (Delhi)
- **Mid-level Drivers**: Range from 11.96% (Delhi) to 13.22% (Bengaluru) - Highest overall

| Metric | Mean | Median | Std Dev | Min | Max | Q1 | Q3 |
|--------|------|--------|---------|-----|-----|----|----|
| Experience_Months | 32.01 | 33.00 | 16.21 | 3 | 59 | 18.00 | 46.00 |
| Avg_Rating | 4.30 | 4.33 | 0.39 | 3.6 | 5.0 | 3.96 | 4.63 |
| Total_Rides_Last_30_Days | 162.49 | 162.50 | 79.55 | 30 | 299 | 93.00 | 230.25 |
| Avg_Battery_Consumption_km | 0.174 | 0.180 | 0.027 | 0.13 | 0.22 | 0.150 | 0.200 |
| Cancellation_Rate_% | 11.76 | 12.09 | 4.99 | 3.09 | 19.99 | 7.37 | 16.10 |

### City-Specific Statistics

**Mumbai** (88 drivers):
- Mean Experience: 32.65 months | Mean Rating: 4.28 | Mean Rides: 151.69
- Median Cancellation Rate: 11.93%

**Bengaluru** (108 drivers):
- Mean Experience: 31.20 months | Mean Rating: 4.24 | Mean Rides: 159.60
- Median Cancellation Rate: 12.04%

**Delhi** (99 drivers):
- Mean Experience: 33.81 months | Mean Rating: 4.35 | Mean Rides: 167.86
- Median Cancellation Rate: 12.15%

**Hyderabad** (105 drivers):
- Mean Experience: 30.59 months | Mean Rating: 4.33 | Mean Rides: 169.44
- Median Cancellation Rate: 12.18%

### Advanced Statistics
- **Skewness**: All variables near 0 (range: -0.09 to 0.01), indicating symmetric distributions
- **Kurtosis**: All variables negative (range: -1.13 to -1.24), indicating platykurtic (flatter) distributions
- **Pearson Correlations**: All correlations weak (|r| < 0.10), indicating variable independence
- **ANOVA Tests**: Results indicate statistical sign (400 drivers, 0 duplicates, 0 missing values)
2. **City Variations**: Moderate differences across cities (Delhi highest cancellation at 12.13%, Hyderabad highest rides at 17,791)
3. **Experience Paradox**: Experience shows NO correlation with ratings (r = -0.01), challenging conventional wisdom
4. **Variable Independence**: Weak correlations across all metrics (|r| < 0.10) suggest multifactorial performance drivers
5. **Mid-Career Challenge**: Mid-level drivers (21-40 months) consistently show highest cancellation rates
6. **Geographic Efficiency**: Hyderabad demonstrates optimal performance (highest rides, lowest cancellations)
7. **Delhi Advantage**: Delhi shows strongest battery efficiency correlation with experience (r = -0.17)

### Business Implications

**Critical Insights**:
1. **Experience isn't everything**: Since experience doesn't correlate with ratings, focus on training quality over tenure
2. **The mid-career dip**: Target interventions specifically for drivers with 21-40 months of experience
3. **City-specific strategies**: 
   - Hyderabad model should be studied for best practices
   - Delhi's battery efficiency patterns merit replication
   - Mumbai's balanced metrics suggest stable operations
4. **Ride volume vs quality**: Hyderabad proves high volume and low cancellations can coexist

### Recommendations

**Immediate Actions**:
1. **Address mid-career cancellations**: Implement support programs for drivers with 21-40 months experience
2. **Replicate Hyderabad's success**: Study and implement Hyderabad's operational practices across other cities
3. **Delhi efficiency training**: Export Delhi's battery efficiency techniques to other cities
4. **Experience-agnostic quality**: Since experience doesn't predict ratings, emphasize continuous training over tenure bonuses

**Strategic Initiatives**:
5. **Independent metric management**: As metrics don't correlate, develop separate improvement programs for each
6. **City benchmarking**: Establish Delhi as rating benchmark (4.35), Hyderabad as volume benchmark (169 rides/driver)
7. **Optimal experience-rating combinations**: Target high-experience, low-rating drivers for performance coaching (lowest cancellations at 10.79%)

**Monitoring**:
8. Track the 0.59% cancellation rate gap between best (Hyderabad 11.54%) and worst (Delhi 12.13%) cities
9. Monitor if experience remains uncorrelated with performance over time
10. Regular quarterly reviews to validate these patterns persist
#### Key Performance Patterns

For each city, statistical summaries reveal:
- **Sample Sizes**: Number of drivers per city
- **Mean Values**: Average performance across metrics
- **Median Cancellation Rates**: Central tendency of cancellation behavior
- **Mean Ratings**: Average driver quality per city
- **Mean Total Rides**: Activity levels by city

---

## Statistical Summary

### Distribution Characteristics
- All numeric variables analyzed for central tendency (mean, median, mode)
- Spread measures calculated (standard deviation, variance)
- Quartiles and ranges determined

### Advanced Statistics
- **Skewness**: Measures distribution asymmetry
- **Kurtosis**: Indicates distribution tail weight
- **Pearson Correlations**: Linear relationships quantified
- **ANOVA Tests**: Categorical group differences validated

---

## Conclusion

### Overall Findings
1. **Data Integrity**: Dataset is clean and complete, suitable for analysis
2. **City Variations**: Significant differences exist across cities in all metrics
3. **Experience Matters**: Driver experience correlates with various performance indicators
4. **Complex Relationships**: Three-way interactions reveal nuanced patterns
5. **Market Segmentation**: Different cities require tailored strategies

### Business Implications
- **Driver Recruitment**: Target optimal experience levels per city
- **Quality Improvement**: Focus on factors correlating with higher ratings
- **Retention Strategies**: Address cancellation rate patterns
- **Resource Allocation**: Optimize based on city-specific patterns
- **Training Programs**: Design experience-appropriate training

### Recommendations
1. Investigate high cancellation rates in specific cities
2. Develop city-specific driver management strategies
3. Monitor experience vs performance trends
4. Implement targeted interventions based on trivariate patterns
5. Regular analysis updates to track changes over time

---

## Methodology

### Analysis Types Performed
1. **Univariate Analysis**: Individual variable distributions and statistics
2. **Bivariate Analysis**: Two-way relationships and correlations
3. **Trivariate Analysis**: Three-way interactions and complex patterns

### Visualization Techniques
- Histograms
- Box plots
- Density (KDE) plots
- Scatter plots with trend lines
- Bar charts
- Correlation heatmaps
- 3D scatter plots
- Interaction heatmaps

### Statistical Tests
- Descriptive statistics
- Correlation analysis (Pearson)
- ANOVA tests for categorical relationships
- Covariance analysis
- Skewness and kurtosis calculations


