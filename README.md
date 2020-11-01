# Coursera_Capstone

# Clustering Neighborhoods in Canada
Coursera Capstone Project

## Introduction
Canada is among the countries with a high immigration rates and in recent years it has become one of the most popular destination for educated professionals and skilled labor. In 2019 alone, Canada welcomed 341,000 immigrants and recently as per the new announcements it will be accepting over 400,000 immigrants per year between 2021-2023. This increase is to meet the economic growth targets and to replace the retiring workforce. Since Canada is a huge country standing at 9.985 Million Km2, relocation for immigrants thus poses a huge challenge. 
In this project, we will create a tool which will assist the immigrants in identifying different habitable and populated areas within Canada across all its provinces. In addition, we will segment the neighborhoods across different regions based on most common venues in the neighborhoods. This will enable the immigrants to quickly identify the regions and neighborhoods best suited for their purpose.

## Data
To address the problem in question we will be using the location coordinates of major neighborhoods of Canada across all the provinces. This data can be downloaded for Canada from http://download.geonames.org/export/zip/. The data is in a tabular format so it can be read straight into pandas data frame. We will be using **Postal Code** (column 2), **Place Name** (column3), **Province Name** (column4), **Latitude** (column 10) and **Longitude** (column 11).
In addition, we will also be leveraging on Foursquare location data to pull in the most popular neighboring venues for each of the locations. We will achieve this through Foursquare APIs by passing the latitude and longitude location of each of the neighborhood into the ‘explore’ function below.
url= 'https://api.foursquare.com/v2/venues/explore?&client_id={}&client_secret={}&v={}&ll={},{}&radius={}&limit={}'.format(CLIENT_ID, CLIENT_SECRET, VERSION, LATITUDE ,LONGITUDE, RADIUS, LIMIT)
Where:
- CLIENT_ID and CLIENT_SECRET => Users credentials for Foursquare application
- LATITUDE, LONGITUDE  => Location coordinates of the neighborhood
- RADIUS => Distance in meters within which to search for venues
- LIMIT => Maximum number of venue results to return
