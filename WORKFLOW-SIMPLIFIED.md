##Workflow - Simplified

This workflow is a simplified step by step guide to to display OSM data using the layers and stylesheet provided in this repository and optimise the speed at which the data is processed and displayed in ArcGIS in stages. It uses the purpose built models based on the OpenStreetMap Editor for ArcGIS toolbox that remove the need to a user to put in a number of paramters, such as tag names.

For a more detailed workflow showing exactly what happens at each step, see [WORKFLOW-EXTENDED.md](https://github.com/GASCUK/OpenStreetMap-ArcGIS/blob/master/WORKFLOW-EXTENDED.md).

1. [Downloading and processing the data](https://github.com/GASCUK/OpenStreetMap-ArcGIS/blob/master/WORKFLOW.md#downloading-and-processing).

###Downloading and processing the data

1. Download the raw OSM data for the area of interest from [Geofabrik](http://download.geofabrik.de/). 
 1. Whole continents can be downloaded if necessary but it is not recommended due to the time they take to process. If only a specific country is required then it is much more preferable to download just this data instead. (Note: For example, the whole of Africa took us over 7 days to download and process whereas Cyprus took less than a couple of hours).
 2. Download the *.bz2 compressed OSM file and unzip. If this file is corrupt then download the *.pbf and use the openly available [OSMConvert](http://wiki.openstreetmap.org/wiki/Osmconvert) tool to convert the *.pbf to a *.osm file.
