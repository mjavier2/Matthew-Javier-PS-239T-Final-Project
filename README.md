# Matthew-Javier-ps239t-final-project (under construction!)

## Description
    This project focuses on creating a risk terrain model for crime in New York City. In this project, I will analyze petit larceny in April of 2017 and investigate certain geographical risk factors. These factors will be limited to infrastructural assets that I find to be strongly associated with New York's citylife: subways, bus stops, and munimeters. Because the distribution of these assets are concentrated in the most population dense precincts, I will throw in public libraries as sort of an ad hoc control variable since these are located relatively equality across the precincts. This long term project will eventually include other considerable risk factors. 

    Onto the process itself. The datasets are sourced from NYC's Open Data R is used to clean the raw crime data, cutting out unimportant columns and isolating the data down to April 2017's petit larceny incidents. Then I began to clean the precinct data by merging the populations and shape area columns into one, to which I then calculated the pop density per squar mile. Once this was done I loaded the datasets (crime, precinct, subway, bus, wifi, munimeter, library) into QGIS. In QGIS I ran a KNN algorithm called the distance matrix located in the vector analysis tool between petit larcenies and each variable. I also used the count points in polygon feature to find out how many larcenies and variables existed in each precinct. From here I merged the distance results into the petitlarceny dataframe while the polygon counts were merged with the precinct data. From here, I aggregated each precincts larcenies' distances to x variable and then merged the means and medians into the the precinct dataframe. I then created a separate dataset, precinct_summary, to display the average characteristics of each precinct. Another dataset was formed from the main precincts one to hold the per capita larenies and per capita of x variable. Once this was done, I did some visualization with ggplot2. I compared several variables such as pop density and distance to subway entrance. Each comparison had the absolute numbers of x variable as well as positions relative to other precincts. After this I conducted some statistical analysis with the t.test and cor.test functions of R. 

## Dependencies
1. R, version 3.4.4
2. RStudio, version 1.1442
2. QGIS, version 3.0.1

## Files
### Data
#### Infrastructure Data
1.nypp.csv: NYPD precinct multipoint polygons. Note, precinct 61 was a broken polygon, I literally drew the precinct by hand to solve this. Available here: https://data.cityofnewyork.us/Public-Safety/Police-Precincts/78dh-3ptz:
2. nypd_precincts_and_2010_census_pop.csv/shp: NYPD precincts with 2010 census population. This data is used to calculate the population density. Available here: https://dunnguyen.carto.com/tables/nypd_precincts_and_2010_census_pop/public
    Note: the .cpg, .dbf, .prj, .shx all need to be in the same folder of the shp file to be uploaded into QGIS
3. DOITT_SUBWAY_ENTRANCE_01_13SEPT2010.csv: Subway entrance locations, available here: https://data.cityofnewyork.us/Transportation/Subway-Entrances/drex-xx56. 
4. Bus_Stop_Shelter.csv: Dataset with bus stop shelters, available here: https://data.cityofnewyork.us/Transportation/Bus-Stop-Shelters/qafz-7myz
5. MUNIMETER.csv: Dataset with the locations of the multi-space meters (Kiosk meters where you buy a pass and place it in your dashboard). Available here: http://www.systemicpeace.org/inscrdata.html
6. NYC_Free_Public_WiFi_03292017.csv: Dataset for all public wifi hotspots. Available here: https://data.cityofnewyork.us/Social-Services/NYC-Wi-Fi-Hotspot-Locations/a9we-mtpn
7. LIBRARY.csv: Locations of public libraries, available here: https://data.cityofnewyork.us/Business/Library/p4pf-fyc4/data
*Note that the filenames from NYC Open Data say they are outdated. They continuously update, but fail to rename the file.
#### Crime data
1. NYPD_Complaint_Data_Current_YTD.csv: All reported crimes that occurred in New York City limits, available here: https://data.cityofnewyork.us/Public-Safety/NYPD-Complaint-Data-Current-YTD/5uac-w243
    - NYPD_Incident_Level_Data_Column_Descriptions.csv for column descriptions
2. petitlarceny4.17.csv: Github limits uploads to 100mb, the above dataset is too big so here is an abridged version with only April and select columns of interest.

### Code

1. 01_Matt-Javier-CleaningData.rmd: Loads and cleans data from NYC Open Data, also merges data produced from QGIS
2. 02_Matt-Javier-Analysis.rmd: Further distills precinct data, constructs graphs, and also checks the statistics.

### Results
1. subwayentrance2population.pdf: Graph comparing number of subway entrances to precinct's pop density.
2. Bus2population.pdf: Graph comparing bus stop shelters to pop density.
3. wifilocations2population.pdf: Graph comparing wifi hotspots to pop density.
4. munimeters2population.pdf: Graph comparing number of munimeters to pop density.
5. libraries2population.pdf:Graph comparing number of public libaries to precincts pop density.
6. MeanVariableDistance2Larceny.pdf: Graphs the mean variable distances from a larceny with regards to each precinct.
Note: All graphs that have been uploaded are the relative positions among precincts.
The following are maps produced from QGIS
7. precinctsbylarcenies.png: Precinct heatmap of larcenies.
8. subwayentrances.png: Locations of subway entrances.
9. busstopshelters.png: Locations of bus stop shelters.
10. wifilocations.png: Locations of wifi locations.
11. munimeters.png: Locations of munimeters.
libraries.png: Locations of public libraries.
12. NYC_MAP.qgis: Map with all the different layers in it. Also if you load it, you need to make sure you select the one that ends in 
".qgis" not ".gis~". As with the shp file, all these file have to be present in the same folder.
## More Information

Include any other details you think your user might need to reproduce your results. You may also include other information such as your contact information, credits, etc.
