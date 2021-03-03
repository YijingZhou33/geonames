# Retrieving Coordinates and Hierarchy from GeoNames

Some metadata in the BTAA Geoportal includes place names, but does not include coordinates. For these records, users cannot use the map search to discover the approximate geographical area of the target data. Automating a process to add coordinates has two benefits: 

1. The old-fashioned way is to add it manually, which is extremely time-consuming and error-prone. 
2. Adding geographical hierarchy to metadata would make the search engine return related results when searching for place names.

*<a href="https://github.com/BTAA-Geospatial-Data-Project/geonames">Original Repository</a>*



## GeoNames

**<a href='http://www.geonames.org/'>GeoNames</a>** is a database available for downloading geographical names as well as other information. All the features are categorized into one out of 9 [feature classes](https://www.geonames.org/export/codes.html).

- #### Implementation

  It provides a Python library named [GeoNames](https://geocoder.readthedocs.io/providers/GeoNames.html) which supports several methods to retrieve geographic information, hierarchy, and children for a given GeoName. 

- #### Drawback

  The search results do not guarantee the accuracy and always return the first record. It also does not support searching for the exact match. There is a great chance of ending up with the mismatch. 

  

## Workflow
- #### Raw data - *<a href="https://github.com/YijingZhou33/geonames/blob/main/data/sample/sample.csv">Sample</a>*

  As usual, the csv file is formatted in the GeoBlacklight Template. The required columns include “**Title**”, “**Slug**” and “**Spatial Coverage**”. It can also export fields like “**Download**” and “**Information**” to the final product if applicable. 

- #### Python scripts - *<a href="https://github.com/BTAA-Geospatial-Data-Project/geonames/blob/main/fetch.ipynb">Sample</a>*

  It will pull URI, coordinates, hierarchy based on place name (“**Spatial Coverage**”) from the GeoNames database, and then export to a new csv file. 



- #### Final products - *<a href="https://github.com/YijingZhou33/geonames/blob/main/data/sample/sample_done.csv">Sample</a>*

