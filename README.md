# Isodistance Schools Greece 
The isodistance_schools_Greece repository contains the calculated isodistance zones of all the secondary education school units of Greece (Gymnasia & Lykeia), as well as the location of said schools, and maps it out in a Github page. The isodistance zones were calculated using the [openrouteservice](https://openrouteservice.org/) (ORS) and further processed in QGIS to take into account locations that have little or zero road coverage.  The data of the list of active schools and their geographic locations are from the [panhellenic school network](https://www.sch.gr/), which is the interet service provider (ISP) of the Greek ministry of Education.  

The page is created in index.html, with the data sources being the geojson files for the polygons and points data. In the index.html we use the [Open Source Routing Machine](https://project-osrm.org/) (OSRM) to calculate the closest school from a point on a map that's part of the analysed area.  

## geojson_files directory
The directory contains all the .geojson files that are required for the map. 
1. gymnasia-isodistances: isodistance zones for all the Gymnasia of the regions of interest
2. lykeia-isodistances: the isodistance zones for all the Lykeia
3. gymnasia_locations: the point geometry that contains all the locations of the Gymnasia schools and their names
4. lykeia_locations: the locations of all Lykeia schools
5. islands-without-schools: contains the polygon geometry of all the islands (of the regions of interest) that do not have a school on their territory

## isodistance_example_notebook
An .ipynb notebook that contains three cells and is a standalone pipeline for the reading of the schools data, the sampling of a specific area or type of school (in our example we used Zakynthos for location and Lykeia). You need to have a valid [openrouteservice](https://openrouteservice.org/) key to run this code. By changing the variables in the first cell you can choose your location or type of school of interest. 

## index.html
The main code file that visualizes the data in an interactive map. There are two versions of the map text components, one in Greek and one in English, and they change upon clicking the lang-switch button. When clicking anywhere the OSRM finds the closest school and calculates the distance and the route to said school. 

**Note:** The distance calculated from OSRM is not always the same as the one calculated from ORS when designating the areas in each isodistance category, since they may take different routes to reach a destination.  

When clicking anywhere outside the polygons the OSRM is not activated, and the user gets a placeholder text.

## schools_list_Greece
The .xlsx file that contains the data from the panhellenic school network. It contains all the schools and administrative units of Greece that have been labeled as "active" and are not categorized as in "suspended activity" («σε αναστολή»). 
