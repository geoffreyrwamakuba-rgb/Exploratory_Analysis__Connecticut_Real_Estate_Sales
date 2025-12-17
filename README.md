# Connecticut Real Estate Sales EDA (1999–2024)
Exploratory Data Analysis of 1.1M+ real estate transactions in Connecticut.
Completed in Python (Pandas, NumPy, Matplotlib, Seaborn) to uncover long-term trends in pricing, property types and towns.

## Key Questions, Charts & Analysis

### 1. How have sales price trends changed over the 2001–2023 period overall, by Property Type and Town?
#### 1.1. Overall
![alt text](https://github.com/geoffreyrwamakuba-rgb/Exploratory-Analysis---20-years-of-US-Real-Estate-data/blob/main/1.1%20Connecticut_property_sales_over_time.png?raw=true)

#### Observations
- Clear Sales volatility throughout years
- 2007–2011: The US housing crash (Sales decline --> Slow recovery --> Credit tightening, Foreclosures, Reduced transaction volumes)
- 2012–2019: steady recovery phase (Market stabilisation supported by sustained low interest rates)
- 2020–2022: Historically low mortgage rates and demand shifts contribute to rapid price appreciation
- 2022–2023: Rising interest rates, elevated inflation, and affordability constraints dampen momentum

#### 1.2 By Property Type
![alt text](https://github.com/geoffreyrwamakuba-rgb/Exploratory-Analysis---20-years-of-US-Real-Estate-data/blob/main/1.2%20Sales_trends_by_property_type.png?raw=true)

#### Observations
- 1 & 2 Family properties consistently dominate sales value across the entire period
- Apartments/Condos and 3–4 Family properties form a stable secondary tier 
- Their trajectories broadly mirror residential cycles, suggesting similar demand drivers (interest rates, affordability, household formation)
- Non-resi property types (Comm, Indus, Utility, Vacant Land) show limited activity prior to ~2018 followed by a noticeable increase over the last 5 years

#### 1.3 By Town
![alt text](https://github.com/geoffreyrwamakuba-rgb/Exploratory-Analysis---20-years-of-US-Real-Estate-data/blob/main/1.3%20Sales_over_time_for_top_10_towns.png?raw=true)

![alt text](https://github.com/geoffreyrwamakuba-rgb/Exploratory-Analysis---20-years-of-US-Real-Estate-data/blob/main/1.4%20Median_sales_by_town.png?raw=true)

#### Observations
- **The top 10 towns collectively account for ~37% of total sales value**
  - Sales are concentrated in affluent towns (Greenwich, Darien, Westport, and Stamford)
  - This reflects persistent demand for premium residential living
- **Greenwich consistently leads sales, driven by high-value transactions rather than volume alone**
- **Bridgeport and Danbury show relative contraction, reflecting more reliance on volume than high per-sale value**

### 2.1 How does sale price vary with assessed value?
![alt text](https://github.com/geoffreyrwamakuba-rgb/Exploratory-Analysis---20-years-of-US-Real-Estate-data/blob/main/2.1%20Sales_vs_value_scatter_plot_(log_scale).png?raw=true)

#### Observations
- **Strong positive Correlation of 0.71**
- **Residential properties show the tightest clustering around the trend line**
  - Assessments are a relatively good predictor of market values
  - This reflects more standardised valuation methods and more homogeneous property characteristics in the resi market
- **Commercial and “Other” properties exhibit greater dispersion**
  - Assessments are a weaker predictor of market values.
  - This indicates that sale prices are more sensitive to other factors (deal structure, zoning and redevelopment options)

### 2.2 Does property type influence the % Profit on Sale?
![alt text](https://github.com/geoffreyrwamakuba-rgb/Exploratory-Analysis---20-years-of-US-Real-Estate-data/blob/main/2.2.%20%25_Profit_Distribution_by_Property_Type.png?raw=true)

#### Observations 
- **Residential properties exhibit tighter and more symmetric profit distributions**
  - After removing extreme outliers, residential properties show a relatively narrow interquartile range, with median profit margins being modestly positive (~50-70%)
  - This suggests strong price discovery and competitive pricing in high-volume housing markets
- **Commercial and “Other” property types display wider dispersion and higher upside variability**
  - Even with fliers removed, commercial and other non-resi property types exhibit broader profit distributions
  - This reflects the heterogeneity of these assets, where sale outcomes depend on other factors  as seen before (redevelopment potential, income streams, zoning changes)

### 3.  Which towns or regions have the highest sale price over the years?
![alt text](https://github.com/geoffreyrwamakuba-rgb/Exploratory-Analysis---20-years-of-US-Real-Estate-data/blob/main/3.%20Filled%20Map.png?raw=true)

#### Observations
- **Southwestern Connecticut clearly dominates median sale prices**
  - Towns in Fairfield County (Greenwich, Darien, New Canaan, Westport, Weston) have the highest median sale values, clustered around $1.5–$1.7m
  - These towns are part of the **NYC commuter belt**, with direct rail access to Manhattan via Metro-North
  - They are consistently ranked among the wealthiest towns in the US by median household income and net worth
- **Price gradients weaken rapidly moving inland**
  - Much of central and eastern Connecticut shows sub-$700k medians, with many towns closer to $400–600k
  - Inland towns are:
    - Less connected to NYC labour markets
    - More dependent on local or regional employment
    - Eastern Connecticut has historically experienced slower population and income growth, particularly post-manufacturing decline

### 4.1 How do median household income, education levels, or poverty rates correlate with prices and sales activity?
![alt text](https://github.com/geoffreyrwamakuba-rgb/Exploratory-Analysis---20-years-of-US-Real-Estate-data/blob/main/4.%20Demographics_correlation_heatmap.png?raw=true)

#### Observations
- **As expected, income and education are highly correlated**
- **Socioeconomic variables show only weak linear relationships with sales outcomes**
  - Median household income, education level, and poverty rate all exhibit very weak correlations (|r| < 0.15) with sales ratios or sale values
  - Property prices are more strongly driven by: Property-specific characteristics (size, location within town, quality) & Market dynamics
- **Sales ratio behaves differently from absolute sale values**
  - Sales Ratio Calculated shows zero / near-zero correlations with socioeconomic variables compared to absolute sale values
  - Assessments may already partially account for local income differences
  - Deviations from assessed values are driven more by market dynamics

### 5. How did COVID-19 pandemic years affect sale prices and volumes in Connecticut?
![alt text](https://github.com/geoffreyrwamakuba-rgb/Exploratory-Analysis---20-years-of-US-Real-Estate-data/blob/main/5.%20COVID%20YoY%20growth.png?raw=true)

#### Observations
- **YoY metrics are used here to remove seasonality and isolate structural shocks**
- **Sales value growth is significantly more volatile than sales volume**
  - Sales value YoY has extreme swings (>100% during 2020–2021 and <−60% in 2022), while sales volume remains comparatively stable
  - This indicates that price effects, rather than changes in transaction counts, were the dominant driver of total sales fluctuations
  - This highlights how supply shortages, bidding pressure, and shifts toward higher-value properties amplified sales value independently of deal volume
- **COVID produced an abnormal price-led cycle rather than a volume-led one**
  - This behaviour contrasts with typical downturns, which usually show volume declines first and sustained price weakness

### Data Cleaning & Preparation
- Removed rows with missing or invalid sale dates, prices, or assessed values
- Standardised town names, dates, and data types
- Removed duplicates
- Replaced inconsistent Sales Ratio with a calculated % Profit on Sale
- Consolidated Residential records using detailed residential sub-types

### Tools & Technologies
- **Python:** pandas, numpy
- **Visualization:** matplotlib, seaborn
- **Data Sources:**
  - Connecticut Real Estate Sales (2001–2023) - [Data.gov](https://catalog.data.gov/dataset/real-estate-sales-2001-2018)
  - CPI data from the [Federal Reserve (FRED)](https://fred.stlouisfed.org/series/CPIAUCSL)
