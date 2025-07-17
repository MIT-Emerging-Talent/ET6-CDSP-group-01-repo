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
  `Year`, `City`, `Rainfall_mm`  
  Each row represents annual rainfall for a specific city.

### ⚠️ Possible Limitations of the Rainfall_mm Dataset

- Possible inaccuracies due to the reliance on satellite and sparse ground
  station data across Africa.
- Errors may have occurred during the extraction process, affecting data quality.

---

## 🌆 Urban Extent

The data was collected by pasting [code](https://code.earthengine.google.com/788e28603790ffed166540e8730c39ad?noload=1),
 which was AI-generated, into the Google Earth Engine [code editor](https://code.earthengine.google.com/).
 The data was saved into Google Drive, in a `.csv` format.
 The sources used include:

- **MODIS** (2005–2020)  
- **Dynamic World** (2021–2025)

### 📁 Structure of the Urban Extent Dataset

- **Raw Data**:  
  `system:index`, `city`, `source`, `urban_area_sqkm`, `year`, `.geo`

- **Cleaned Data**:  
  `year`, `city`, `urban_area_sqkm`

### ⚠️ Possible Limitations of the Urban Extent Dataset

- The use of two different sources may introduce inconsistency across years.
- Satellite data is prone to inaccuracies, especially in the presence of cloud cover.

---

## 🌊 Flood Water Extent

The data was collected by pasting [code](https://code.earthengine.google.com/3dae86a50830daf2b0854acddd21d95b?noload=1),
which was AI-generated, into the Google Earth Engine [code editor](https://code.earthengine.google.com/).
The data was saved into Google Drive, in a `.csv` format. The source used to
collect the data from in the Google Earth Engine is Sentinel-1. The timeframe of
 the data collected is from 2015-2025.

### 📁 Structure of the Flood Water Extent Dataset

- **Raw Data**:  
  `system:index`, `city`, `flood_water_extent (km^2)`, `month`, `source`, `.geo`

- **Cleaned Data**:  
  `year`, `city`, `flood_water_extent (km^2)`

### ⚠️ Possible Limitations of the Flood Water Extent Dataset

- Lack of ground truth data may impact accuracy.
- Flooded vegetated areas may be undetected by satellite, resulting in underestimation.
- Missing data from **2005 to 2014**, which makes historical flood cause analysis
   limited.

---

## 🧩 Merged (Master) Dataset

This dataset combines the three individual datasets using **Jupyter Notebook**
scripts and Python libraries such as `pandas`.

### 📁 Structure of the Merged Dataset

`year`, `city`, `flood_water_extent_(km^2)`, `rainfall_mm`, `urban_area_sqkm`
