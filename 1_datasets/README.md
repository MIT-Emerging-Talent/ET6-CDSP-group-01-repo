# 📊 Datasets Documentation

## 🌧️ Rainfall_mm

The rainfall dataset was initially downloaded from
[CHIRPS](https://data.chc.ucsb.edu/products/CHIRPS-2.0/) as
[Africa monthly](https://data.chc.ucsb.edu/products/CHIRPS-2.0/africa_monthly/)
rainfall in [.tiffs format](https://data.chc.ucsb.edu/products/CHIRPS-2.0/africa_monthly/tifs/)
 for the time frame of **2005–2025**.
Data for **Addis Ababa** and **Kampala** was extracted using Python
libraries such as `rasterio` and `pandas`, then saved in `.csv` format.

### 📁 Structure of the Rainfall_mm Dataset

- **Raw Data**:  
  `City`, `Date`, `Year`, `Month`, `Rainfall_mm`

- **Cleaned Data**:  
  `City`, `Year`, `Rainfall_mm`  
  Each row represents annual rainfall for a specific city.

### ⚠️ Possible Limitations of the Rainfall_mm Dataset

- Possible inaccuracies due to the reliance on satellite and sparse ground
  station data across Africa.
- Errors may have occurred during the extraction process, affecting data quality.

---

## 🌆 Urban Extent

---

## 🌊 Flood Water Extent

The raw data was collected by pasting [code](https://code.earthengine.google.com/3dae86a50830daf2b0854acddd21d95b?noload=1),
which was AI-generated, into the Google Earth Engine [code editor](https://code.earthengine.google.com/).
The data was saved into Google Drive, in a `.csv` format. The source used to
collect the data from in the Google Earth Engine is Sentinel-1. The timeframe of
 the raw data collected is from 2015-2025.

As for the cleaned data, the timeframe of `2005-2014` is of **synthetic data**.

### 📁 Structure of the Flood Water Extent Dataset

- **Raw Data**:  
  `system:index`, `city`, `flood_water_extent (km^2)`, `month`, `source`, `.geo`

- **Cleaned Data**:  
  `city`, `year`, `is_synthetic`, `Total Flood Extent (km^2)`

### ⚠️ Possible Limitations of the Flood Water Extent Dataset

- Lack of ground truth data may impact accuracy.
- Flooded vegetated areas may be undetected by satellite, resulting in underestimation.

---

## 🧩 Merged (Master) Dataset

This dataset combines the three individual datasets using **Jupyter Notebook**
scripts and Python libraries such as `pandas`.

### 📁 Structure of the Merged Dataset

`City`, `Year`, `Rainfall_mm`, `Total_Flood_Extent_km2`, `Urban_Area`
