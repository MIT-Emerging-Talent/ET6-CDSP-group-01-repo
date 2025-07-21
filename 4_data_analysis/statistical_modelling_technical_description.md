# **Technical Description of the** statistical modelling notebook

This [notebook](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/4_data_analysis/statistical_modelling.ipynb)
details the statistical analysis performed to investigate the relationship
between increasing urban area and flood extent in **Addis Ababa** and **Kampala**.

---

## 1. Objective

The analysis aims to quantify the relationship between **urbanization**
(`Urban_Area`) and **flood severity** (`Total_Flood_Extent_km²`), while
accounting for influential factors such as **rainfall** and city-specific differences.

---

## 2. Data Preparation and Preprocessing

The dataset consists of **42 observations** (21 years × 2 cities) and includes
the following key variables:

- `City`: Categorical variable (Addis Ababa, Kampala)
- `Urban_Area`: Total urban land area (in km²)
- `Rainfall_mm`: Annual rainfall (in millimeters)
- `Total_Flood_Extent_km2`: Flooded area (dependent variable)

### 2.1 Preprocessing Steps

- **Boolean columns removed**: Flags like `is_synthetic_rainfall` were dropped
  to focus the model on continuous, interpretable predictors.
- **Column renaming**: `Total Flood Extent (km^2)` was renamed to
  `Total_Flood_Extent_km2` to ensure compatibility with the `statsmodels`
   formula syntax, which requires clean column names for parsing.

---

## 3. Modeling Approach and Reasoning

An **Ordinary Least Squares (OLS)** regression was selected for its interpretability
and effectiveness in modeling continuous outcomes.

### Model 1: City-Specific Urbanization Effects

**Formula:**

`Total_Flood_Extent_km2 ~ Urban_Area * C(City) + Rainfall_mm`

This model tests whether the impact of urbanization on flood extent differs by city:

- `C(City)` enables separate intercepts (baseline flood levels) for each city.
- The interaction term `Urban_Area * C(City)` examines whether the slope of
  urbanization’s effect varies between cities.
- `Rainfall_mm` serves as a control, acknowledging that rainfall is a direct
  driver of flooding.

### Model 2: Urban-Rainfall Interaction

After observing unintuitive results in Model 1, a second model was specified:

**Formula:**

`Total_Flood_Extent_km2 ~ Urban_Area * Rainfall_mm + C(City)`

This model explores whether urban areas **amplify the effect** of rainfall on flooding:

- Urban surfaces reduce natural infiltration, potentially increasing runoff
  from the same amount of rainfall.
- The interaction term `Urban_Area * Rainfall_mm` captures this amplification.
- `C(City)` controls for unobserved, city-specific baseline differences.

---

## 4. Results and Interpretation

### Model 1 Findings

- **Unexpected negative main effect**: The coefficient for `Urban_Area` was
  significantly negative (−2.52e-05, *p* < 0.001), suggesting that greater
  urban area is associated with *less* flooding. This contradicts established
  hydrological expectations.
- **No city-specific slope difference**: The interaction
  `Urban_Area:C(City)[T.Kampala]` was not significant (*p* = 0.780),
  indicating similar urban-flood relationships across both cities.
- **High multicollinearity**: The model showed a very high
  **Condition Number (4.59e+09)**, suggesting that the predictors are strongly
  correlated—likely impairing the reliability of the estimated coefficients.

### Model 2 Findings

This alternative model revealed a more meaningful interpretation:

- **Significant interaction**: The term `Urban_Area:Rainfall_mm` was positive
  and significant (1.47e-08, *p* = 0.011).
- **Interpretation**: As urban area increases, the impact of rainfall on flood
  extent becomes stronger. Even if the main effect of `Urban_Area` remained
  negative (due to multicollinearity), the interaction term captured the
  expected dynamic—urbanization intensifies rainfall-induced flooding.
- **Visualization**: An interaction plot demonstrated that the difference in
  flood extent between high and low rainfall scenarios becomes
  **more pronounced** as urban area increases. This visual representation
  reinforces the idea of an amplifying effect.

---

## 5. Critical Evaluation and Limitations

Despite some valuable insights, several methodological issues limit the strength
of the conclusions:

- **Severe multicollinearity**: The models suffer from inflated variance due to
  strong correlations among predictors. Urban area likely serves as a proxy for
  **time**, which also correlates with potential improvements in flood control
  systems—confounding the effect.
- **Non-physical coefficient**: The negative main effect of `Urban_Area` lacks
  physical plausibility and complicates interpretation. It likely reflects
  overlapping trends with other variables.
- **Small dataset**: With only 42 observations, the models are vulnerable
  to influence from outliers and lack statistical power for detecting subtler effects.

---

## 6. Alternative Approaches and Future Work

To overcome these challenges, several methodological improvements can be explored:

### 6.1 Addressing Multicollinearity

- **First-difference transformation**: Modeling the **change** in flood extent,
  rather than absolute levels, isolates short-term effects and minimizes the
  influence of long-term trends.
- **Mean-centering**: Centering `Urban_Area` and `Rainfall_mm` prior to creating
   the interaction term can reduce collinearity and improve interpretability.

### 6.2 Advanced Modeling Techniques

- **Panel data models**: Given the panel structure (cities observed over time),
  Fixed Effects or Random Effects models can control for unobserved,
  time-invariant characteristics of each city.
