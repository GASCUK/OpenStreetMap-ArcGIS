##Workflow

There is a specific workflow that needs to be followed in order display OSM data using the layers and stylesheet provided in this repository and optimise the speed at which the data is processed and displayed in ArcGIS.

###Instructions

1. Download the raw OSM data for the area of interest from [Geofabrik](http://download.geofabrik.de/). 
 1. Whole continents can be downloaded if necessary but it is not recommended due to the time they take to process *(the whole of Africa takes over 7 days to download and process whereas Cyprus takes less than a couple of hours)*. If only a specific country is required then it is much more preferable to download just this data instead.
 2. Download the *.bz2 compressed OSM file and unzip. If this file is corrupt then download the *.pbf and use the openly available [OSMConvert](http://wiki.openstreetmap.org/wiki/Osmconvert) tool to convert the *.pbf to a *.osm file.
2. Load the *.osm file using the 'Load OSM' tool within the ArcGIS Editor for OpenStreetMap toolset.
 1. Name the feature dataset 'planet'.
