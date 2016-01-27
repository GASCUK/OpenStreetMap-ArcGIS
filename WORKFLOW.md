##Workflow

There is a specific workflow that needs to be followed in order display OSM data using the layers and stylesheet provided in this repository and optimise the speed at which the data is processed and displayed in ArcGIS.

###Instructions

1. Download the raw OSM data for the area of interest from [Geofabrik](http://download.geofabrik.de/). 
 1. Whole continents can be downloaded if necessary but it is not recommended due to the time they take to process. If only a specific country is required then it is much more preferable to download just this data instead. (Note: the whole of Africa took us over 7 days to download and process whereas Cyprus took less than a couple of hours).
 2. Download the *.bz2 compressed OSM file and unzip. If this file is corrupt then download the *.pbf and use the openly available [OSMConvert](http://wiki.openstreetmap.org/wiki/Osmconvert) tool to convert the *.pbf to a *.osm file.
2. Load the osm file using the **Load OSM** tool in the *ArcGIS Editor for OpenStreetMap* toolset.
 1. ----insert image here
 2. Create a file geodatabase in your workspace.
 2. Name the *Target feature dataset* "planet" in this gdb.
 3. Expand the optional *Adjust Input Schema* parameter and add the required OSM tag keys to schema:
    * admin_level
    * bridge
    * content
    * craft
    * drinking_water
    * emergency
    * ford
    * generator:source
    * office
    * pump
    * religion
    * seasonal
    * tower:type
    * tunnel
 4. Running this tool results in a feature dataset in the file gdb called planet containing three feature classes: planet_osm_ln, planet_osm_ply and planet_osm_pt.
3. Use the **OSM Attribute Selector** tool in the *ArcGIS Editor for OpenStreetMap* toolset on each of the three feature classes in turn to extract OSM keys from the tag collection and store them as standalone attributes.
 1. ----insert image here
 2. Select 'All' in the *OSM Tag Keys* parameter
