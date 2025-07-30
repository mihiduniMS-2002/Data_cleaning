
# 🧹 Data Cleaning Report: Hotel Booking Demand Dataset

## Executive Summary
This report outlines the data cleaning process applied to the **Hotel Booking Demand Dataset** from Kaggle. The goal was to prepare a clean, analysis-ready dataset by addressing missing values, duplicates, outliers, and inconsistencies.

Key cleaning actions included:
- Filling missing values in `agent`, `company`, `country`, and `children`
- Removing 500+ duplicate records
- Detecting and treating outliers in columns like `adr` and `lead_time`
- Fixing rows with impossible guest counts (zero total guests)

## Data Quality Assessment

**Original Dataset:**
- **Rows**: 119,390  
- **Columns**: 32  
- **Missing Values**: Present in 4+ columns  
- **Duplicates**: ~500 rows  
- **Outliers**: Found in `adr`, `lead_time`, `adults`

**Identified Issues:**

| Issue           | Affected Columns              | Severity |
|----------------|-------------------------------|----------|
| Missing Values | children, agent, company, country | Medium   |
| Duplicates     | All                           | High     |
| Outliers       | adr, lead_time                | High     |
| Inconsistencies| guests = 0, arrival date format | Medium   |

## Cleaning Methodology

**1. Missing Values:**
- `children`: Replaced NaN with 0  
- `agent`, `company`: Replaced NaN with 0  
- `country`: Replaced NaN with "Unknown"

**2. Duplicates:**
- Removed 500+ exact duplicate rows using `df.drop_duplicates()`.

**3. Outliers:**
- Used IQR method to detect and remove extreme values in `adr`, `lead_time`, and guest columns.

**4. Inconsistencies:**
- Removed rows where `adults + children + babies == 0`
- Parsed `arrival_date` using combined date columns
- Standardized values in categorical columns

## Results and Impact

| Metric             | Before Cleaning | After Cleaning |
|--------------------|-----------------|----------------|
| Rows               | 119,390         | ~118,000       |
| Columns            | 32              | 32             |
| Missing Values     | Present         | Handled        |
| Duplicates         | 500+            | 0              |
| Outliers           | Present         | Treated        |
| Zero Guest Rows    | Present         | Removed        |

The cleaned dataset is now consistent, complete, and ready for further analysis or machine learning.

## Recommendations

- Ensure guest information is always entered (avoid zero guests)
- Reduce reliance on agents and companies with missing data
- Standardize input fields to prevent inconsistent values


https://github.com/mihiduniMS-2002/Machine_learning.git :- GitHub link