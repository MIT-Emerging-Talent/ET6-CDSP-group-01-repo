# Data Exploration

This folder contains comprehensive exploratory data analysis (EDA) notebooks for
understanding the **rainfall** and **flood water extent** patterns in **Kampala,
 Uganda** and **Addis Ababa, Ethiopia**.

---

## Overview

The data exploration phase focuses on two critical datasets that form the
foundation of our climate and flood risk analysis:

- **[Rainfall Data](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/raw_data/Rainfall_Data.csv)**
  — Monthly precipitation measurements spanning **2005–2025**
- **[Flood Water Extent Data](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/raw_data/Monthly_Flood_Water_Extent_Kampala_Addis_2015_2025_km2.csv)**
   — Monthly flood coverage measurements from **2015–2025**

---

## Notebooks

### 1. [`rainfall_data_eda.ipynb`](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/3_data_exploration/rainfall_data_eda.ipynb)

#### 1.1 Dataset Overview

- **Time Period**: 2005–2025 (21 years)  
- **Records**: 490 monthly observations  
- **Cities**: Kampala, Uganda and Addis Ababa, Ethiopia  
- **Variables**: City, Date, Year, Month, Rainfall (mm)  

#### 1.2 Key Findings

- **Data Quality**: Complete dataset with no missing values or duplicates  
- **Overall Statistics**:  
  - Mean rainfall: **101.16 mm**  
  - Standard deviation: **84.6 mm**  

- **City Comparison**:
  - **Kampala**:  
    - More consistent rainfall  
    - Mean: **105.57 mm**
  - **Addis Ababa**:  
    - Higher variability  
    - Mean: **96.75 mm**

- **Outliers**: 33 extreme rainfall events (6.73% of data), ranging from
  **282–402 mm**  
- **Seasonality**: Clear monthly patterns with peak rainfall varying by city  

#### 1.3 Analysis Sections

- Data loading and initial setup  
- Data structure and quality assessment  
- Descriptive statistics by city and month  
- Temporal trend analysis  
- Comparative analysis between cities  

---

### 2. [`flood_data_eda.ipynb`](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/3_data_exploration/flood_data_eda.ipynb)

#### 2.1 Dataset Overview

- **Time Period**: 2015–2025 (11 years)  
- **Records**: 250 monthly observations  
- **Cities**: Kampala, Uganda and Addis Ababa, Ethiopia  
- **Variables**: City, Flood Water Extent (km²), Month  

#### 2.2 Key Findings

- **Data Quality**: Complete dataset with no missing, negative, or zero values  
- **Overall Statistics**:  
  - Mean flood extent: **131.94 km²**  
  - Standard deviation: **79.0 km²**  

- **City Comparison**:
  - **Kampala**:  
    - Higher average flood extent: **174.03 km²**  
    - Lower variability: **CV: 27.13%**
  - **Addis Ababa**:  
    - Lower average flood extent: **90.52 km²**  
    - Higher variability: **CV: 90.77%**

- **Outliers**: 1 extreme event (**440.31 km²**) representing **0.40%** of data
- **Distribution**:
  - **Kampala**: Negative skewness (**-1.349**)  
  - **Addis Ababa**: Positive skewness (**1.269**)

#### 2.3 Analysis Sections

- Data loading and initial setup  
- Data structure and quality assessment  
- Descriptive statistics by city and month  
- Temporal trend analysis  
- Comparative analysis between cities

### Data Quality Summary

| Dataset       | Records | Missing Values | Duplicates | Outliers       |
|---------------|---------|----------------|------------|----------------|
| [Rainfall](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/raw_data/Rainfall_Data.csv)      | 490     | 0              | 0          | 33 (6.73%)     |
| [Flood Extent](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/raw_data/Monthly_Flood_Water_Extent_Kampala_Addis_2015_2025_km2.csv)  | 250     | 0              | 0          | 1 (0.40%)      |
