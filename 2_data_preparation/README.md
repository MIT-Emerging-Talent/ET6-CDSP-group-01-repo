# 📊 Data Preparation

## 📓 Jupyter Notebooks Used

### 🌊 `clean_flood_water_extent_kampala_addis.ipynb`

This notebook cleans the raw data of monthly flood water extent by;

- Removing unnecessary columns.
- Sorting the rows so each row has coordinates for each city of the same year.
- Re-arranging the variables in the order year, city,
- Adding in the column of year.
- Summing the total flood that occurs in each year.
- Keeping only rows for the years `2015-2020`.

This notebook creates and saves the cleaned
 [flood water extent](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/cleaned_data/yearly_flood_water_extent_kampala_addis_2015_2020.csv)
  data.

---

### 🌆 `clean_urbanextent_kampala_addis.ipynb`

This notebook is for cleaning the urban extent raw data for Kampala and Addis Ababa.

It does so by;

- Removing unnecessary columns.
- Sorting the rows so each row has coordinates for each city of the same year.
- Re-arranging the variables in the order `year, city, urban are per square kilometer`
- Keeping only rows of years `2015-2020`

This notebook creates and saves the cleaned
 [urban extent](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/cleaned_data/urbanextent_kampala_addis_cleaned.csv)
  data

---

### 🌧️ `cleaning_rainfalldata.ipynb`

This notebook cleans the raw rainfall data by;

- Removing unnecessary columns.
- Finding the total sum of the rainfall that has occurred in each year.
- Reordering the column names in the order `year, city, rainfall-mm`
- Sorting the rows in ascending order so each row has coordinates for each city
 of the same year.

This notebook creates and saves the cleaned
 [rainfall](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/cleaned_data/cleaned_rainfalldata.csv)
  data.

---

### 🔗 `merge_all_datasets.ipynb`

This notebook merges all the three cleaned datasets.

For the variables with same names across all the datasets, this notebook
 ensures all the names are the same (in small letters) across all three first,
  before merging.

This notebook creates and saves the cleaned [all merged data](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/cleaned_data/merged_flood_rainfall_urban_extent.csv).

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

This notebook creates and saves the raw [rainfall data](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/1_datasets/raw_data/Rainfall_Data.csv)
