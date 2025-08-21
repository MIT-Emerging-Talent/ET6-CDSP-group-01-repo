# 📊 Datasets Documentation

## 🌧️ Rainfall_mm

The rainfall [dataset](https://drive.google.com/drive/folders/1mZhWEGfSIZ_lcjlARw6krktrlgfLcG5T)
 was initially downloaded from
[CHIRPS](https://data.chc.ucsb.edu/products/CHIRPS-2.0/) as
[Africa monthly](https://data.chc.ucsb.edu/products/CHIRPS-2.0/africa_monthly/)
rainfall in [.tiffs format](https://data.chc.ucsb.edu/products/CHIRPS-2.0/africa_monthly/tifs/)
 for the time frame of **2005–2025**.
Data for **Addis Ababa** and **Kampala** was extracted using Python
libraries such as `rasterio` and `pandas`, then saved in `.csv` format.

### 📁 Structure of the Rainfall_mm Dataset

- [**Raw Data**](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/raw_data/Rainfall_Data.csv):

  `City`, `Date`, `Year`, `Month`, `Rainfall_mm`

- [**Cleaned Data**](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/clean_data/yearly_rainfall.csv):

  `City`, `Year`, `Rainfall_mm`  
  
  Each row represents annual rainfall for a specific city.

### ⚠️ Possible Limitations of the Rainfall_mm Dataset

- Possible inaccuracies due to the reliance on satellite and sparse ground
  station data across Africa.
- Errors may have occurred during the extraction process, affecting data quality.

---

## 🌆 Urban Extent

The raw data was sourced from the [Global Human Settlement Layer](https://human-settlement.emergency.copernicus.eu/).
 You can download the data by clicking on the `download GHSL data` which brings
  you to this [page](https://human-settlement.emergency.copernicus.eu/download.php).
   Here, you click on `GHS-UCDB`,and under`By Thematic Domain`, select GHSL.

Given that the data obtained is global, values specific to Kampala and Addis
 Ababa were filtered within excel and saved as the [raw data](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/raw_data/GHSL_excel.xlsx).

### 📁 Structure of the Urban Extent Dataset

- [**Raw Data**](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/raw_data/GHSL_excel.xlsx):
  
`ID_UC_G0`, `GC_UCN_MAI_2025`, `GC_CNT_GAD_2025`, `GC_UCA_KM2_2025`,
 `GC_POP_TOT_2025`, `GC_DEV_WIG_2025`, `GC_DEV_USR_2025`, `GH_BUS_TOT_1975`,
  `GH_BUS_TOT_1980`, `GH_BUS_TOT_1985`, `GH_XST_D30_2020`, `GH_XST_D11_2025`,
   `GH_XST_D12_2025`, `GH_XST_D13_2025`, `GH_XST_D21_2025`, `GH_XST_D22_2025`,
    `GH_XST_D23_2025`, `GH_XST_D30_2025`, `GH_L30_2025`, `GH_W30_2025`

A detailed overview of the meaning of the indicator names can be found in the
 downloaded dataset folder, in the file of **GHS_UCDB_R2024_Online_lite.pdf**.
  In the `pdf` document, the explanations start on the heading **Fact Sheets Specimen**.

- [**Cleaned Data**](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/clean_data/Urban_synthetic_data.csv):
  
`Cities`, `Year`, `Urban_Area`, `is_synthetic`

### ⚠️ Possible Limitations of the Urban Extent Dataset

- Struggles with small-scale urban features
- Limited field validation in remote/conflict zones.

---

## 🌊 Flood Water Extent

The raw data was collected by pasting [code](https://code.earthengine.google.com/3dae86a50830daf2b0854acddd21d95b?noload=1),
which was AI-generated, into the Google Earth Engine [code editor](https://code.earthengine.google.com/).
The data was saved into Google Drive, in a `.csv` format. The source used to
collect the data from in the Google Earth Engine is Sentinel-1. The timeframe of
 the raw data collected is from 2015-2025.

As for the cleaned data, the timeframe of `2005-2014` is of **synthetic data**.

### 📁 Structure of the Flood Water Extent Dataset

- [**Raw Data**](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/raw_data/Monthly_Flood_Water_Extent_Kampala_Addis_2015_2025_km2.csv):

  `system:index`, `city`, `flood_water_extent (km^2)`, `month`, `source`, `.geo`

- [**Cleaned Data**](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/clean_data/flood_synthetic_data.csv):

  `city`, `year`, `is_synthetic`, `Total Flood Extent (km^2)`

### ⚠️ Possible Limitations of the Flood Water Extent Dataset

- Lack of ground truth data may impact accuracy.
- Flooded vegetated areas may be undetected by satellite, resulting in underestimation.

---

## 🧩 [Merged (Master) Dataset](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/clean_data/merged_data_new2.csv)

This dataset combines the three individual datasets using **Jupyter Notebook**
scripts and Python libraries such as `pandas`.

### 📁 Structure of the Merged Dataset

`City`, `Year`, `Rainfall_mm`, `Total_Flood_Extent_km2`, `Urban_Area`
