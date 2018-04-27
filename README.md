# Matthew-Javier-ps239t-final-project (under construction!)

## Description
This project focuses on creating a risk terrain model for crime in New York City. In this project, I will analyze petit larceny in April of 2017 and investigate certain geographical risk factors. These factors will be limited to infrastructural assets that I find to be strongly associated with New York's citylife: subways, bus stops, and munimeters. Because the distribution of these assets are concentrated in the most population dense precincts, I will throw in public libraries as sort of an ad hoc control variable since these are located relatively equality across the precincts. This long term project will eventually include other considerable risk factors. 
Onto the process itself. The datasets are sourced from NYC's Open Data R is used to clean the raw crime data, cutting out unimportant columns and isolating the data down to April 2017's petit larceny incidents. Next begin to 

Give a short, 1-2 paragraph description of your project. Focus on the code, not the theoretical / substantive / academic side of things. 

## Dependencies

1. R, version 3.4.4
2. RStudio, version 1.1442
2. QGIS, version 3.0.1

## Files

### Data
#### Infrastructure Data
1.nypp.csv: NYPD precinct multipoint polygons. Note, precinct 61 was a broken polygon, I literally drew the precinct by hand to solve this. Available here: https://data.cityofnewyork.us/Public-Safety/Police-Precincts/78dh-3ptz:
2. nypd_precincts_and_2010_census_pop.csv: NYPD precincts with 2010 census population. This data is used to calculate the population density. Available here: https://dunnguyen.carto.com/tables/nypd_precincts_and_2010_census_pop/public
3. DOITT_SUBWAY_ENTRANCE_01_13SEPT2010.csv: Subway entrance locations, available here: https://data.cityofnewyork.us/Transportation/Subway-Entrances/drex-xx56. 
4. Bus_Stop_Shelter.csv: The PolityVI dataset, available here: https://data.cityofnewyork.us/Transportation/Bus-Stop-Shelters/qafz-7myz
5. MUNIMETER.csv: Dataset with the locations of the multi-space meters (Kiosk meters where you buy a pass and place it in your dashboard). Available here: http://www.systemicpeace.org/inscrdata.html
6. NYC_Free_Public_WiFi_03292017.csv: Dataset for all public wifi hotspots. Available here: https://data.cityofnewyork.us/Social-Services/NYC-Wi-Fi-Hotspot-Locations/a9we-mtpn
9. LIBRARY.csv: The PolityVI dataset, available here: http://www.systemicpeace.org/inscrdata.html

*Note that the filenames from NYC Open Data are outdated. They continuously update, but fail to rename the file.
#### Crime data
1. NYPD_Complaint_Data_Current_YTD.csv: All reported crimes that occurred in New York City limits, available here: https://data.cityofnewyork.us/Public-Safety/NYPD-Complaint-Data-Current-YTD/5uac-w243
    - NYPD_Incident_Level_Data_Column_Descriptions.csv for column descriptions

### Code

1. Matt-Javier-CleaningData.rmd: Loads and cleans data from NYC Open Data, also merges data produced from QGIS
2. Matt-Javier-Analysis.rmd: Loads, cleans, and merges the raw Polity and NYT datasets into the Analysis Dataset.

### Results

1. precinctsbylarcenies.png
2. regression-table.txt: Summarizes the results of OLS regression, modelling *nyt* on a number of covariates.

## More Information

Include any other details you think your user might need to reproduce your results. You may also include other information such as your contact information, credits, etc.
