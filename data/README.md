### Contents
* air_walk_merged_clean.csv
Final dataset used to model all locations. Outputted by 02_EDA.ipynb. 
Contains transformed and cleaned data.

* air_walk_merged_clean_la.csv
Final dataset used to model Los Angeles. Outputted by 02_EDA.ipynb. 
This is the above dataset filtered to the CSA Los Angeles-Long Beach-Anaheim.

a: Original Data
- Contains the untouched data as gathered from the EPA and Purple Air APIs

b: LA Data
- Contains the merged data gathered from the EPA and Purple Air APIs, selected for the Los Angeles metropolitan area and all of its respective CSAs and CBSAs. 
- One DataFrame will include just the walkability data, and the other includes the air quality data for Los Angeles, with a third dataframe presenting the merged result of the former two.
