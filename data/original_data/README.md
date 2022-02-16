The files in this directory are

* **purpleair_original.csv**: This is the raw data taken from the [PurpleAir API](https://github.com/ReagentX/purple_air_api). 
Columns with NAs are dropped and the latitude longitudes are bounded in a box of the United States.
This is the output of the file 00_purple_air_scrape.ipynb.

* **purpleair_fips.csv**: This is the purpleair_original.csv file with a column added for fips code. This 
is the output of 01_data_merge.ipynb.

* **air_walk_merged.csv**: This is an inner join of purpleair_fips.csv with the air walkability dataset taken from (https://www.epa.gov/smartgrowth/smart-location-mapping).
