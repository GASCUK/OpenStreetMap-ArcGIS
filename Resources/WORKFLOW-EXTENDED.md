##Workflow - Extended

This workflow is a detailed step by step guide to to display OSM data using the layers and stylesheet provided in this repository and optimise the speed at which the data is processed and displayed in ArcGIS in stages. It only uses the tools provided in the OpenStreetMap Editor for ArcGIS toolbox and gives details on exactly what needs to be input for each tool to work.

For a more simplified workflow using [models](https://github.com/GASCUK/OpenStreetMap-ArcGIS/tree/master/Models), see [WORKFLOW-SIMPLIFIED.md](https://github.com/GASCUK/OpenStreetMap-ArcGIS/blob/master/Resources/WORKFLOW-SIMPLIFIED.md).

1. [Downloading the data](https://github.com/GASCUK/OpenStreetMap-ArcGIS/blob/master/Resources/WORKFLOW-EXTENDED.md#downloading-the-data).
2. [Processing the data](https://github.com/GASCUK/OpenStreetMap-ArcGIS/blob/master/Resources/WORKFLOW-EXTENDED.md#processing-the-data).
3. [Completing the data set](https://github.com/GASCUK/OpenStreetMap-ArcGIS/blob/master/Resources/WORKFLOW-EXTENDED.md#completing-the-data-set).
4. [Creating an MXD and displaying the processed data in ArcMap](https://github.com/GASCUK/OpenStreetMap-ArcGIS/blob/master/Resources/WORKFLOW-EXTENDED.md#creating-an-mxd-and-displaying-the-processed-data-in-arcmap).

###Downloading the data

1. Download the raw OSM data for the area of interest from [Geofabrik](http://download.geofabrik.de/). 
 1. Download the .bz2 compressed OSM file. _(**Note 1:** Whole continents can be downloaded if necessary but it is not recommended due to the time they take to process. If only a specific country is required then it is much more preferable to download just this data instead. **Note 2:** If the .bz2 file is corrupt then download the .pbf and use the openly available [OSMConvert](http://wiki.openstreetmap.org/wiki/Osmconvert) tool to convert the .pbf to a .osm file)_.
 2. Unzip the .bz2 file.

###Processing the data

1. In ArcCatalog, load the .osm file using the **Load OSM** tool in the *ArcGIS Editor for OpenStreetMap* toolset, located in *System Toolboxes* in ArcGIS.
 1. ![Load OSM tool](https://raw.githubusercontent.com/GASCUK/OpenStreetMap-ArcGIS/master/Images/LoadOSMFile.png)
 2. Select the unzipped .osm file in *Load OSM*.
 3. Create a file geodatabase and name the *Target feature dataset* into which the OSM data will be loaded "planet" within this gdb.
 4. Expand the optional *Adjust Input Schema* parameter and add the required OSM tag keys to schema:
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
    * The following tags are optional. They are required for a network dataset. Adding these tags at this stage speeds up the creation of the network dataset if it is required:
      * access
      * construct
      * maxheight
      * maxspeed
      * proposed
      * smoothness
      * surface
 5. Running this tool results in a feature dataset in the selected file gdb called planet containing three feature classes; planet_osm_ln, planet_osm_ply and planet_osm_pt.
3. If a network dataset is required, see [NETWORK.md](https://github.com/GASCUK/OpenStreetMap-ArcGIS/blob/master/Resources/NETWORK.md) for information on this step.
4. In ArcCatalog, use the **OSM Attribute Selector** tool in the *ArcGIS Editor for OpenStreetMap* toolset on each of the three feature classes in turn to extract OSM keys from the tag collection and store them as standalone attributes.
 1. ![OSM Attribute Selector tool](https://raw.githubusercontent.com/GASCUK/OpenStreetMap-ArcGIS/master/Images/OSMAttributeSelector.png)
 2. Select 'EXISTING_TAG_FIELDS' in the *OSM Tag Keys* parameter and run the tool.
5. Create attribute indexes for each of the three feature classes within the planet feature dataset.
 1. In ArcCatalog, run the **Add Index Attributes** tool on each of the feature classes and select the following for each individual one:
       * **planet_osm_ln**: aeroway, barrier, highway, osm_bridge, osm_ford, osm_seasonal, osmSupportingElement, power, railway, route, waterway.
       * **planet_osm_ply**: aeroway, amenity, building, highway, landuse, leisure, man_made, natural, osmSupportingElement, tourism, waterway.
       * **planet_osm_pt**: amenity, barrier, highway, leisure, man_made, natural, osm_admin_level, osm_content, osm_craft, osm_drinking_water, osm_emergency, osm_generator_58_source, osm_office, osm_pump, osm_religion, osm_tower_58_type, osmSupportingElement, place, power, shop, tourism.

###Completing the data set
1. Add the [Natural Earth bathymetry data](https://github.com/GASCUK/OpenStreetMap-ArcGIS/blob/master/Data/README.md) and the [OSM dissolved land polygon](https://github.com/GASCUK/OpenStreetMap-ArcGIS/blob/master/Data/README.md) to the file geodatabase alongside the processed OSM data.

###Creating an MXD and displaying the processed data in ArcMap
1. Open ArcMap and add the Humanitarian OSM [stylesheet](https://github.com/GASCUK/OpenStreetMap-ArcGIS/tree/master/Styles): *Customize > Style Manager > Styles... > Add Style to List...*
2. Create a new blank MXD and load the [layers](https://github.com/GASCUK/OpenStreetMap-ArcGIS/tree/master/Layers).
2. Arrange the layers in numerical order.
3. Close ArcMap. Within ArcCatalog, set the MXD data source to the file geodatabase where the processed OSM data has been loaded into.
4. Reopen the MXD in ArcMap to view the symbolised OSM data.
