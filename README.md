# Project 4: Walkability & Air Quality in Los Angeles

### Problem Statement:
This is a regression problem that predicts whether the walkability of the Los Angeles area correlates with air quality. The goal of this analysis is to determine if areas of high walkability are also areas with good air quality -- particularly within the Los Angeles area whose walkability and air quality can vary depending on accessibility to public transit, forest fires, and proximity to the ocean.  

Looking at the [U.S. EPA Walkability Index](https://edg.epa.gov/metadata/catalog/search/resource/details.page?uuid=%7B251AFDD9-23A7-4068-9B27-A3048A7E6012%7D) which highlights the walkability of a region (using census data from 2017-2019 and other data sources) and air quality data pulled from the [PurpleAir API](https://github.com/ReagentX/purple_air_api), we are hoping to determine if regions (CBSAs & CSAs) with high walkability also have good air quality.     

Our stakeholders are families who want to move to Los Angeles in an area of both good walkability and good air quality.

### Executive Summary: 
Our team started the project with the goal of predicting air quality given walkability across the United States with the ultimate goal of determining if a CBSA & CSA region with high walkability would also have good air quality.  Our goal is to help our stakeholders who are families who want to to move to different regions across the country. Doing this type of analysis required merging a number of datasets including the EPA's 2021 walkability index dataset along with an air quality dataset. Initially, we opted to use the EPA's annual air quality index dataset. However, merging these two datasets proved challenging because the data within the walkability dataset was much more localized than the air quality data -- we could not merge the data without omitting large sections of the walkability dataset or finding ways to generate more granualar data for the air quality dataset.

In searching for more granular air quality data, we came across a company called PurpleAir, which sells air quality monitors to everyday conusumers. We scraped their API to grab all the metrics of their air quality data, keeping our focus on the USA. The air quality data was The Los Angeles area proved to be an interesting choice because it is both large and diverse enough to provide a mixed outlook on air quality and walkability throughout different neighborhoods -- with some regions being metro accessible, some being near the ocean and others being subject to the ongoing fires and arid conditions that unfortunately plague much of California. 



### Contents: 

#### Folders:

I: Data 
- Contains raw, collected, intermediate and cleaned data used in the project.

II: Scratch Work
- Unpolished, draft code.

#### Files:
* 00_purple_air_scrape.ipynb
Collects purple air sensor network data using the [Purple Air API](https://github.com/ReagentX/purple_air_api). 

* 01_data_merge.ipynb
Adds fips code to purple air data using the [FCC Block API](https://geo.fcc.gov/api/census/#!/block/get_block_find) and merges with the walkability dataset.

* 02_EDA_correlations.ipynb
* Correlations used to explore data and confirm target choice on raw, unscrubbed data.

* 02_EDA_Steven.ipynb
Removes extra columns, imputes missing values, and transforms data.

* 03_airton_project4_viz_clean_data.ipynb
Visualization EDA, scatter plots against air quality, feature correlation lists, box & violin plots.

* 03_modeling.ipynb
Linear regression modelling with Sequential Feature Selection on full and LA dataset.


### Data Sources:
##### Air Quality:
The air quality data from obtained from the PurpleAir API.  It contained latitude, longitude, indoor/outdoor indicator, daily temperature, humidity and pressure readings in addition to the average weekly measure of PM2.5 particles.  This data was pulled from the PurpleAir website using the PurpleAir API.

Purple air data is concentrated in California. The largest regions are San Francisco, Los Angeles, Sacramento, distantly followed by Denver and New York.
The full dataset included <> distinct locations.

##### Walkability:
The walkability data is also published by the EPA and can be downloaded at (https://www.epa.gov/smartgrowth/smart-location-mapping).
This data includes metrics in five primary categories - density, diversity, design, transit accessiblity, and destination asseccibility - and combines them in an overall walkability index. 

#### [Data Dictionary](https://docs.google.com/spreadsheets/d/1r2PsolJEZtMx6HIJzTZFNOOO5BFDuejNbNi8Xu0Aalg/edit#gid=0) for the full data dictionary -- Our data merges the walkability and airquality index on CBSAs


### Modeling
We built linear regression models with a focus on building sparse and interpretable models. 
Therefore we did not use the full feature set in our final models, even though they had a better score. 

#### Model Comparison
| Model | r2 score |
| :-: | :-: |
| Baseline | 0.0 |
| 6 Features (National Model) | 0.268 |
| 5 Interpretable Features (LA) | 0.347 |
| 8 Features (LA) | 0.368 |
| 57 Features (LA) | 0.443 |Comparison

Additionally, focusing on, focusing on just 1 region LA, makes it easier to model than the full dataset.

#### LA Model

| Feature | Expected Change in log AQI per unit |
| :-: | :-: |
| Log of Working Age Population Within 45 Minutes Car Commute | 0.1843 |
| Proportion of Jobs in<br />Office Sector | 0.0036 |
| Proportion of Jobs in<br />Industrial Sector | 0.0028 |
| 2+car Households  | -0.0046 |
| Log of Census Block Group Acreage | -0.0799 |

Top 5 features selected to optimize score.
sequential feature selection (greedily) optimizes score for a small feature set.
Additionally removed highly correlated features.

Overall, several features suggest that suburban areas have better air quality including Two car households, area, and working age population within 45 minute commute.

#### Limitations

* Any changes in calculations to the EPA walkability features will impact our model. Dataset is difficult to build, published every 5-10 years.
* PurpleAir sensors are not represtantively distributed by geography or wealth.
* Air quality varies considerably by time, weather, season, and local wildfire status
* 1 week average does not completely capture the nuance of air quality / harms on public health.
* There is a lot of variance, and much of it can’t be explained by demographic variables we considered in our analysis

### Conclusion:
Air quality is a key environmental factor determining public and personal health and quality of life. It can play a role in deciding where to live.

Air quality varies considerably across California
LA > San Francisco > Sacramento


Suburban regions have better air quality than urban ones
Despite car pollution, more vehicles are associated with better air quality



### Further Study:
