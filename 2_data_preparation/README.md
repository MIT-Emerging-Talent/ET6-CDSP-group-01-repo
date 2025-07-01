# 📊 Data Preparation

## 📓 Jupyter Notebooks Used

### 🌊 `clean_flood_water_extent_kampala_addis.ipynb`

This notebook cleans the raw data of monthly flood water extent by;

- Removing unnecessary columns.
- Adding in values of `'0'` to show unavailable data for the missing years `(2005-2014)`.
- Sorting the rows so each row has coordinates for each city of the same year.
- Re-arranging the variables in the order year, city,
- Adding in the column of year.
- Summing the total flood that occurs in each year.

This notebook creates and saves the cleaned
 [flood water extent](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/cleaned_data/Cleaned_Flood_Water_Extent_Kampala_Addis_2005_2025_km2.csv)
  data.

---

### 🌆 `clean_urbanextent_kampala_addis.ipynb`

This notebook is for cleaning the urban extent raw data for Kampala and Addis Ababa.

It does so by;

- Removing unnecessary columns.
- Sorting the rows so each row has coordinates for each city of the same year.
- Re-arranging the variables in the order `year, city, urban are per square kilometer`

This notebook creates and saves the cleaned
 [urban extent](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/cleaned_data/Cleaned_UrbanExtent_Kampala_Addis.csv)
  data

---

### 🌧️ `cleaning_rainfalldata.ipynb`

This notebook cleans the raw rainfall data by;

- Removing unnecessary columns.
- Finding the total sum of the rainfall that has occurred in each year.
- Reordering the column names in the order `year, city, rainfall-mm`
- Sorting the rows so each row has coordinates for each city of the same year.

This notebook creates and saves the cleaned
 [rainfall](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/cleaned_data/Cleaned_Rainfall_Data.csv)
  data.

---

### 🔗 `mergealldatasets.ipynb`

This notebook merges all the three datasets and also removes the co-ordinates
 of the years `2001-2004`, which were caused by the data from urban extent data,
  that start from the years `2001-2025`, but our research question only needs
   data of the past two decades.

It also creates split files to separate the merged data containing urban extent
 data, sourced from `MODIS` and another containing urban extent data, sourced from
  Dynamic World. To create the split data, the second last cell is tweaked
   according to the specific year period of each data source.

Also, for the variables with same names across all the datasets, this notebook
 ensures all the names are the same across all three first, before merging.

This notebook creates and saves the cleaned [all merged data](https://docs.google.com/spreadsheets/d/1Jal9jb5ZwUZrGC0pOXKH_b52nxxBCSW1otFb7CsmuiQ/edit?gid=213002949#gid=213002949),
 [split merged data__containing urban extent data sourced from MODIS](https://docs.google.com/spreadsheets/d/14mdDBBipwwS_PRjRFkh66fF7CWUMjT77l7UoccDpoHY/edit?gid=573789412#gid=573789412),
  and [split merged data__containing urban extent data sourced from dynamic world](https://docs.google.com/spreadsheets/d/1X-p4Vj-doKN9FZ1191ipbiX-xl7Hgb2tsL1c_x8Lw1w/edit?gid=434186483#gid=434186483)

---

### 🌧️ `extract_chirps_rainfall_kampala_addis`

This notebook extracts raw monthly rainfall data for Kampala and Addis Ababa from
 Africa monthly rainfall data CHIRPS raster `(.tif)` files, using python
  libraries of rasterio and pandas.

It extracts the raw rainfall data by;

- Defining the co-ordinates of the respective cities, to be extracted from the
 `.tiff` files of Africa monthly.

- Defining the paths of the files, one containing the `.tiff` files, and the
 other being the destination file for the extracted raw rainfall data.

- Initializing a list that will hold all the extracted rainfall records being
 they are turned into a **DataFrame**.

- Creating a loop that runs through all the available `.tiff` files, one by
 one, in order.

- Processing only `.tif` files ignoring other file formats and extracting the
 dates from the file names.

- Opening the `.tif` files using the rasterio python library and then loops
 through the respective cities, also extracts the rainfall records of the given
  city coordinates.

- Converting the extracted rainfall records to a dataframe and then saving them.

This notebook creates and saves the raw [rainfall data](https://docs.google.com/spreadsheets/d/1QJptwghbwVuZ4T3hd9GcSUXGe_1U8bK_bMgYSoyGAJQ/edit?gid=621316614#gid=621316614)
