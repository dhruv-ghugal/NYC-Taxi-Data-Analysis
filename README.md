# NYC Yellow Taxi Data Analysis

An end-to-end **Exploratory Data Analysis (EDA)** project on **NYC Yellow Taxi trip data for January 2025**, using Python to analyze trip patterns, distance, duration, passenger behavior, time trends, locations, payment types, vendors, and rate codes.

## Project Overview

This project transforms raw taxi-trip data into meaningful analytical and business insights through:

- Data understanding
- Data quality assessment
- Data cleaning
- Feature engineering
- Exploratory data analysis
- Statistical analysis
- Data visualization
- Business questions
- Advanced analysis
- Final KPI summary

## Dataset

**Dataset:** NYC Yellow Taxi Trip Data  
**Period:** January 2025  
**Format:** Parquet  
**Records:** 3.47 million+ trips  
**Columns:** 20

The dataset contains information such as:

- Pickup and drop-off timestamps
- Passenger count
- Trip distance
- Pickup and drop-off location IDs
- Payment type
- Vendor ID
- Rate code
- Store-and-forward flag
- Trip-related charge fields

## Tech Stack

| Technology | Usage |
|---|---|
| Python | Data analysis |
| Pandas | Data cleaning and analysis |
| NumPy | Statistical and numerical analysis |
| Matplotlib | Visualization |
| Seaborn | Visualization |

## Project Workflow

```text
Raw Taxi Data
      ↓
Data Understanding
      ↓
Data Quality Assessment
      ↓
Data Cleaning
      ↓
Feature Engineering
      ↓
Exploratory Data Analysis
      ↓
Statistical Analysis
      ↓
Business Questions
      ↓
Advanced Analysis
      ↓
Key Findings & Conclusion
```

## Data Cleaning

The project investigates:

- Missing values
- Duplicate records
- Invalid passenger counts
- Zero/negative trip distances
- Invalid timestamps
- Zero-duration trips
- Extremely long trip durations
- Extremely high trip distances

### Cleaning Decisions

- Created a separate `clean_df` DataFrame.
- No duplicate records were found.
- Passenger counts ≤ 0 were converted to missing values.
- Zero/negative distances were investigated but not automatically removed.
- Trips where drop-off occurred before pickup were removed.
- Extreme duration and distance values were investigated as potential data-quality issues.

## Feature Engineering

The following analytical features were created:

- `trip_duration_minutes`
- `pickup_date`
- `pickup_hour`
- `day_of_week`
- `is_weekend`
- `average_speed_mph`
- `distance_category`
- `duration_category`
- `route`

### Duration Categories

| Category | Duration |
|---|---:|
| Very Short | ≤ 5 minutes |
| Short | 5–15 minutes |
| Medium | 15–30 minutes |
| Long | > 30 minutes |

### Distance Categories

| Category | Distance |
|---|---:|
| Short | ≤ 3 miles |
| Medium | 3–10 miles |
| Long | > 10 miles |

## Analysis Performed

### Trip Analysis

- Trip distance distribution
- Trip duration distribution
- Distance vs duration
- Average speed
- Distance and duration outliers
- Passenger-count patterns

### Time Analysis

- Trips by pickup hour
- Trips by day of week
- Weekday vs weekend demand
- Average duration by hour
- Average distance by hour
- Day × hour demand heatmap

### Location Analysis

- Top pickup locations
- Top drop-off locations
- Most common routes
- Route duration analysis
- Route concentration

> `PULocationID` and `DOLocationID` are treated as Taxi Zone IDs rather than neighborhood names.

### Payment Analysis

- Payment type frequency
- Payment type percentage distribution
- Distance by payment type
- Duration by payment type
- Passenger patterns by payment type

### Vendor Analysis

- Vendor trip distribution
- Distance by vendor
- Duration by vendor
- Passenger patterns
- Payment distribution

### Rate Code Analysis

- Rate code frequency
- Average distance by rate code
- Average duration by rate code
- Passenger patterns by rate code

### Store & Forward Analysis

- Store-and-forward distribution
- Distance comparison
- Duration comparison
- Passenger comparison

## Key Findings

- **3,475,102 trips** remained after removing records where drop-off occurred before pickup.
- The busiest pickup hour was **6 PM**.
- The least busy hour was **4 AM**.
- **Thursday** had the highest number of trips.
- Weekday demand was higher than weekend demand.
- The median trip distance was **1.67 miles**.
- The median trip duration was **11.7 minutes**.
- **1 passenger** was the most common passenger count.
- **Credit Card** was the most common payment type.
- Pickup location **161** had the highest trip count.
- Drop-off location **236** had the highest trip count.
- The most common route was **237 → 236**.
- Trip distance and duration showed a **very weak correlation**.
- Several extreme distance, duration, and speed values were identified as potential data-quality issues.

## Advanced Analysis

The project also includes:

- Demand heatmap
- Top 20 routes
- Route duration with a minimum trip-count threshold
- Average-speed investigation
- Distance-band analysis
- Peak vs off-peak comparison
- Route concentration analysis

## Data Quality Limitations

Important limitations identified during the analysis include:

- Missing values in several columns
- Zero/negative trip distances
- Invalid passenger counts
- Extremely large trip distances
- Extremely long trip durations
- Unusually high calculated speeds
- Small sample sizes for some vendor/rate-code groups
- Taxi Zone IDs do not directly provide neighborhood names

These issues were considered when interpreting the results.

## Final KPI Summary

| KPI | Value |
|---|---:|
| Total Trips | 3,475,102 |
| Average Trip Distance | 5.86 miles |
| Median Trip Distance | 1.67 miles |
| Average Trip Duration | 15.03 minutes |
| Median Trip Duration | 11.70 minutes |
| Maximum Trip Distance | 276,423.57 miles |
| Maximum Trip Duration | 5,626.32 minutes |
| Average Speed | 25.74 mph |
| Most Common Passenger Count | 1 |
| Busiest Pickup Hour | 18:00 |
| Busiest Day | Thursday |
| Most Common Payment Type | Credit Card |
| Most Common Pickup Location | 161 |
| Most Common Drop-off Location | 236 |
| Most Common Route | 237 → 236 |

> Maximum distance and duration values are strongly affected by extreme records and should not be interpreted as typical taxi trips.

## Project Files

- `NYC_Taxi_Data_Analysis_Dhruv_Ghugal.ipynb` — Complete analysis, code, outputs, visualizations, and findings.
- `NYC_Taxi_Data_Analysis_Dhruv_Ghugal.pdf` — Final PDF report.

## Author

**Dhruv Sanjay Ghugal**  
B.Tech Computer Engineering
