##Models
A selection of useful models designed to speed up and simplify the method of processing OpenStreetMap data before displaying it in ArcMap, contained within a toolbox.

The individual processes are for each stage of the process of preparing raw OSM data for use in ArcMap. These are useful if you are processing large datasets,

####Includes:
* **Individual processes:**
    * **Load OSM File:** Loads stand alone osm files into a file geodatabase within a feature dataset. The model adds the required OSM tags to the schema and creates a point, polyline and polygon feature class.
    * **OSM Attribute Selector:** Extracts the required OSM keys from the tag collection and stores them as stand alone attributes in the point, polyline and polygon feature classes.
    * **Add OSM Attribute Indexes:** Adds attribute indexes for OSM point, line and polygon feature classes. The model only adds the attribute indexes that are specficially required for that feature class, allowing ArcGIS to quickly locate and match an attribute query, speeding up the display of the data within ArcMap.
* **Complete processes:**
    * **Complete OSM Load Process:** Loads a stand alone osm file into a file geodatabase within a feature dataset, adding the required OSM tags to the schema and creates a point, polyline and polygon feature class. Extracts the required OSM keys from the tag collection and stores them as stand alone attributes. Adds attribute indexes for the feature classes and has the option to create a network dataset if required by the user.
