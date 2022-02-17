# Project 4: Walkability & Air Quality in Los Angeles

### Problem Statement:
This is a regression problem that predicts whether the walkability of the Los Angeles area correlates with air quality. The goal of this analysis is to determine if areas of high walkability are also areas with good air quality -- particularly within the Los Angeles whose walkability and air quality can vary depending on accessibility to public transit, forrest fires, and proximity to the Ocean.
Looking at the [U.S. EPA Walkability Index](https://edg.epa.gov/metadata/catalog/search/resource/details.page?uuid=%7B251AFDD9-23A7-4068-9B27-A3048A7E6012%7D) which highlights the walkability of a region (using census data from 2017-2019) and the [U.S. EPA Air Quality Index (AQI)](https://aqs.epa.gov/aqsweb/airdata/download_files.html), we are hoping to determine if regions (CBSAs & CSAs) with high walkability also have good air quality.     

Our stakeholders are families who want to move to Los Angeles in an area of both good walkability and good air quality.

### Executive Summary:
Our team started the project with the goal of predicting air quality given walkability accross the united states with the ultimate goal of helping determine if a CBSAs & CSAs region with high walkability will also have good air quality in order to help stakeholder and families who want to to move to different regions accross the country. Doing this type of analysis required merging a number of datasets including the EPA's yearly walkability index along with the EPA's annual air quality index. However, merging these two datasets proved challenging because the data within the walkability data frame was much more localized that the air quality data, presenting CSAs and CBSAs at a much more granular level -- we could not merge the data without omitting large sections of the walkability data frame or finding ways to generate more granualar data for the Air Quality dataframe.

To compensate for this gap, we narrowed our scope to one large metropolitan area and searched for open air quality data APIs. Coming accross a company called Purple Air, we were able to scrape their APIs to grab indoor and outdoor air quality date in the Los Angeles area. The Los Angeles ares proved to be and interesting choice because it is both large and diverse enough to provide a mixed outlook on air quality and walkability throughout different neighborhoods -- with some regions being metro accessible, some being near the ocean and others being subject to the ongoing fires and arid conditions that unfortunately plague much of California. 



### Contents: 

#### Folders:

I: Data 
- Contains raw, collected, intermediate and cleaned data used in the project.

III: Gathering & Merging Data
- Import Libraries

IV: EDA
- Import Libraries

V: Modeling
- Import Libraries

VI: Scratch Work
- Import Libraries



### Data Sources:
##### Air Quality:
The air quality data comes from the EPA and is available at (https://aqs.epa.gov/aqsweb/airdata/download_files.html). 
We used annual summary data on the level of concentration by monitor from 2018.
Using the monitor readings is the most granular data available.
Data through 2021 was also available at the time of this project, but we used 2018 data for two reasons.
First, the walkability index is published on a lag so that the most recent index uses raw data primarily from 2017 and 2018.
Second, using 2018 data avoids unusual patterns in the data due to COVID-19.

##### Walkability:
The walkability data is also published by the EPA and can be downloaded at (https://www.epa.gov/smartgrowth/smart-location-mapping).
This data includes metrics in five primary categories - density, diversity, design, transit accessiblity, and destination asseccibility - and combines them in an overall walkability index. 

#### [Data Dictionary](https://docs.google.com/spreadsheets/d/1r2PsolJEZtMx6HIJzTZFNOOO5BFDuejNbNi8Xu0Aalg/edit#gid=0) for the full data dictionary -- Our data merges the walkability and airquality index on CBSAs


### Conclusion:



### Further Study:
