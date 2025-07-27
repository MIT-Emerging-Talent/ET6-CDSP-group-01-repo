# Data Analysis

As cities expand, do floods inevitably get worse?

This folder dives into the complex interplay between urban growth, rainfall, and
flood risk in **Addis Ababa** and **Kampala**, revealing a story of unexpected contradictions.

The `4_data_analysis` folder contains the analytical backbone of our investigation,
housing the notebooks and technical guides that decode the urban flood paradox.

## Summary of Scripts & Notebooks

### [`Comparative_Analysis_Urbanization_and_Flooding_Addis_Kampala.ipynb`](./Comparative_Analysis_Urbanization_and_Flooding_Addis_Kampala.ipynb)   — Uncovering the Urban Flood Paradox

This notebook is where we first confront the puzzle at the heart of our data.
Through a series of visualizations and feature engineering, it reveals why the
relationship between urbanization and flooding is not as simple as it seems.

**Key Discoveries Inside:**

* **A Simpson's Paradox:** The analysis uncovers a classic statistical illusion
  where the combined data shows a positive urban-flood correlation, but
  individual city data reveals a strong *negative* one.
* **Divergent City Profiles:** Boxplots and time-series plots highlight the
   unique signatures of each city, showing that Kampala and Addis Ababa respond
   differently to rainfall and urban expansion.
* **Growth Rate vs. Size:** Feature engineering reveals that the *pace* of urban
   growth (`Urban_Growth_Rate`) is a more potent indicator of immediate flood
   risk than the absolute size of the city.

### [`statistical_modelling.ipynb`](./statistical_modelling.ipynb)   — Quantifying the Rainfall Amplifier Effect

Here, we move beyond visual trends to build statistical proof for our central
hypothesis. This notebook documents the process of modeling flood extent to
isolate the true drivers of risk.

**The Modeling Journey:**

* **A Flawed First Model:** An initial regression model produced a physically
  implausible result (more urban area = less flooding) due to severe
  multicollinearity, highlighting the limitations of a simplistic approach.
* **The Breakthrough Interaction Model:** A second model, designed to test the
  interaction between urban area and rainfall, provided the key insight.
  It found a statistically significant (*p* = 0.011) "amplifier" effect.
* **The Conclusion:** The final model confirms that urban landscapes act as a
  risk multiplier. While the direct effect is complex, a city's primary role in
   flooding is to intensify the damage caused by heavy rainfall. This is
   visualized with an interaction plot showing the effect in action.

### In-Depth Technical Explanations

For a deeper look into the methodology, model diagnostics, and interpretation of
results, please see the detailed technical documents:

* **[`comparative_analysis_technical_description.md`](./comparative_analysis_technical_description.md)**
  – A full walkthrough of the exploratory analysis, feature engineering choices,
   and comparative findings.
* **[`statistical_modelling_technical_description.md`](./statistical_modelling_technical_description.md)**
  – A critical examination of the regression models, their limitations, and the
   reasoning behind the final interaction-based approach.
