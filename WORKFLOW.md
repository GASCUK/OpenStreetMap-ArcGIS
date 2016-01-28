##Workflow

There is a specific workflow that needs to be followed in order display OSM data using the layers and stylesheet provided in this repository and optimise the speed at which the data is processed and displayed in ArcGIS.

###Instructions

1. Download the raw OSM data for the area of interest from [Geofabrik](http://download.geofabrik.de/). 
 1. Whole continents can be downloaded if necessary but it is not recommended due to the time they take to process. If only a specific country is required then it is much more preferable to download just this data instead. (Note: For example, the whole of Africa took us over 7 days to download and process whereas Cyprus took less than a couple of hours).
 2. Download the *.bz2 compressed OSM file and unzip. If this file is corrupt then download the *.pbf and use the openly available [OSMConvert](http://wiki.openstreetmap.org/wiki/Osmconvert) tool to convert the *.pbf to a *.osm file.
2. In ArcCatalog, load the osm file using the **Load OSM** tool in the *ArcGIS Editor for OpenStreetMap* toolset.
 1. ![Load OSM tool](https://raw.githubusercontent.com/GASCUK/OpenStreetMap-ArcGIS/master/Images/LoadOSMFile.png)
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
    * maritime
    * name
    * name:en
    * office
    * oneway
    * pump
    * ref
    * religion
    * seasonal
    * tower:type
    * tunnel
 4. Running this tool results in a feature dataset in the file gdb called planet containing three feature classes: planet_osm_ln, planet_osm_ply and planet_osm_pt.
3. In ArcCatalog, use the **OSM Attribute Selector** tool in the *ArcGIS Editor for OpenStreetMap* toolset on each of the three feature classes in turn to extract OSM keys from the tag collection and store them as standalone attributes.
 1. ![OSM Attribute Selector tool](https://raw.githubusercontent.com/GASCUK/OpenStreetMap-ArcGIS/master/Images/OSMAttributeSelector.png)
 2. Select 'EXISTING_TAG_FIELDS' in the *OSM Tag Keys* parameter and run the tool.
4. Create attribute indexes for each of the three feature classes within the planet feature dataset.
 1. There are two methods of doing this (option b is the fastest):
    1. In ArcCatalog, run the *Add Index Attributes* tool on each of the feature classes and select the following for each individual one:
       * **planet_osm_ln**: aeroway, barrier, highway, osm_bridge, osm_ford, osm_seasonal, osmSupportingElement, power, railway, route, waterway.
       * **planet_osm_ply**: aeroway, amenity, building, highway, landuse, leisure, man_made, natural, osmSupportingElement, tourism, waterway.
       * **planet_osm_pt**: amenity, barrier, highway, leisure, man_made, natural, osm_admin_level, osm_content, osm_craft, osm_drinking_water, osm_emergency, osm_generator_58_source, osm_office, osm_pump, osm_religion, osm_tower_58_type, osmSupportingElement, place, power, shop, tourism.
    2. Run the **Add OSM Attribute Indexes** tool in the [OpenStreetMap Models](https://github.com/GASCUK/OpenStreetMap-ArcGIS/tree/master/Models) toolbox, selecting the three OSM feature classes as inputs.
