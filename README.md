# Isodistance Schools Greece 
The isodistance_schools_Greece repository contains the calculated isodistance zones of all the secondary education school units of Greece (Gymnasia & Lykeia), as well as the location of said schools, and maps it out in a Github page. The isodistance zones were calculated using the [openrouteservice](https://openrouteservice.org/) (ORS) and further processed in QGIS to take into account locations that have little or zero road coverage.  The data of the list of active schools and their geographic locations are from the [panhellenic school network](https://www.sch.gr/), which is the interet service provider (ISP) of the Greek ministry of Education.  

The page is created in index.html, with the data sources being the geojson files for the polygons and points data. In the index.html we use the [Open Source Routing Machine](https://project-osrm.org/) (OSRM) to calculate the closest school from a point on a map that's part of the analysed area.  

