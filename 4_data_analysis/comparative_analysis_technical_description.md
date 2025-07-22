# **Technical Description of the** Comparative Analysis NoteBook

## 1. Notebook Overview

This [notebook](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/4_data_analysis/Comparative_Analysis_Urbanization_and_Flooding_Addis_Kampala.ipynb)
presents the technical steps and findings from an analysis of the relationship
between **urban growth**, **rainfall**, and **flooding** in **Addis Ababa** and **Kampala**.
The goal was to quantify the interaction between these factors and compare the
trends across both cities.

The approach included:

- Data preparation and feature engineering
- Exploratory data analysis (EDA)
- Time series visualization
- Comparative statistical assessments

---

## 2. Analysis Walkthrough and Technical Decisions

### 2.1 Data Loading and Feature Engineering

Several new features were introduced to enhance interpretability and analytical clarity:

- **Urban_Area_km²**: Converted from square meters to square kilometers, making
the figures more readable (e.g., 92.6 km² vs 92,625,150.1 m²).
- **Urban_Growth_Rate**: Calculated as the year-over-year percentage change in
`Urban_Area_km²` for each city using `groupby().pct_change()`. This dynamic
metric captures the pace of urban expansion, not just its size.
- **Flood_Intensity**: Defined as the ratio of flood extent to urban area,
offering insight into how severely urban land is affected by flooding. This
metric accounts for scale differences between cities and normalizes the impact.
- **Standardized Variables (_std)**: Applied Z-score normalization to rainfall,
 flood extent, and urban area using `StandardScaler`. This ensures all features
 are on the same scale, which is especially useful for potential future modeling
 applications.

---

### 2.2 Exploratory & Comparative Analysis

### 2.2.1 Correlation Analysis (Heatmaps)

Correlation matrices were computed using Pearson’s method for both the entire
dataset and individually per city. Visualized using heatmaps with a `coolwarm`
color palette centered at zero, they provided a quick way to assess the
direction and strength of linear relationships.

- A moderate positive correlation (0.58) was found between urban area and flood
  extent when considering both cities together.
- However, analyzing each city separately revealed a strong **negative**
  correlation: -0.74 in Addis Ababa and -0.62 in Kampala. These results
  highlight a potential case of **Simpson’s Paradox**, where the aggregate trend
   masks opposing patterns at the subgroup level. One possible explanation is
   that both cities may have implemented effective flood mitigation measures
   during the period of rapid urbanization.

### 2.2.2 Time Series Analysis (Line Plots)

Time series plots were used to visualize trends in flood extent, rainfall, and
urban area. Dual y-axes were employed to allow rainfall and flood extent to be
displayed together, despite differing units and scales.

- Urban area in both cities showed a consistent upward trend, indicating non-stationarity.
- Rainfall and flood extent appeared more volatile and fluctuated around a mean,
  suggesting a stationary or semi-stationary behavior over the years.

### 2.2.3 Distribution Comparison (Boxplots)

Boxplots were used to compare the distributions of rainfall, flood extent, and
urban area between the two cities. These visualizations made it easy to detect
differences in medians, spreads, and outliers, offering a concise summary of how
these metrics vary across contexts.

---

## 3. Possible Flaws and Limitations

Despite generating valuable insights, the analysis had several limitations:

- **Correlation does not imply causation**: While associations were found,
  they cannot confirm that changes in urban areas *cause* changes in flood extent.
- **Coarse temporal granularity**: Yearly averages likely smooth over short-term
  , high-intensity rainfall events that often drive flooding. Hourly or daily
  data would provide more precise insights.
- **Potential confounding**: The negative correlations found within cities could
  be influenced by unobserved variables, such as policy changes or
  infrastructure improvements.

---

## 4. Alternative and Future Approaches

To improve the analysis, several extensions could be pursued:

- **Statistical hypothesis testing**: The differences observed in boxplots
  could be validated with tests such as the t-test or Mann-Whitney U test to
 determine statistical significance.
- **Stationarity testing**: Formal tests like the Augmented Dickey-Fuller (ADF)
   test could be applied to confirm whether variables like urban area or
   rainfall are stationary over time.
- **Enhanced dataset**: Incorporating data on drainage infrastructure,
  topography, land use from satellite imagery, and population density would
  allow for a more holistic model of flood risk.
