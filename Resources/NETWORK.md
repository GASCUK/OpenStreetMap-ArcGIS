##Create a Network Dataset from OSM Data

A Network Dataset is a dataset that describes the travelling of an agent (e.g., pedestrian, truck driver, cyclist, etc.) along a route. Analyses such as the quickest route between two points, the area of service for a business, what barriers are in the path of a specific route, and more are possible when working with a network dataset. ArcGIS provides tools for such analysis through the Network Analyst extension.

This workflow describes how to use the *ArcGIS Editor for OpenStreetMap* toolsets **Create OSM Network Dataset** tool to create a network dataset from OSM data.

_**Note:** The network will only be as good as the underlying data. Some areas do not have adequate information to facilitate creating a useful network dataset._

###Verify that the Network Analyst extension is checked

The **Create OSM Network Dataset** tool leverages functionality native to the Network Analyst extension. This must be turned on to run the tool successfully. To turn it on, click the "Customize" menu at the top of ArcMap, and select the "Extensions" submenu, then verify that there is a check next to the Network Analyst extension.

###Acquire an OSM feature dataset

Follow the processes detailed in [WORKFLOW-EXTENDED.md]() or [WORKFLOW-SIMPLIFIED.md]() to download a .osm file and load it as a feature dataset.

###Use the Create OSM Network Dataset tool

After acquiring a feature dataset from OSM, and a Network Configuration file, run the **Create OSM Network Dataset** tool. Browse to the tool in the *ArcGIS Editor for OpenStreetMap* toolset, located in the *System Toolboxes*, and double click to launch it.

Fill in the parameters as described below:

1. *Input OSM Feature Dataset:* Browse to the created OSM feature dataset.
2. *Network Configuration File:* The Network Configuration File defines the rules for generating the network dataset from the OSM data. The way the network will be used will determine which config file to use and how to adjust it to better suit ythe requirement. For example, a riverbank can be a barrier if defining a road network, or it can be a thoroughfare if doing ship navigation. There is no automatic way to set these rules, but the OpenStreetMap toolbox contains network configuration sample files can be used to get started. Alternatively, a configuration file can be created from scratch. The OpenStreetMap network configuration sample files can be found at {"\ArcGIS\Desktop10.1\ArcToolbox\Toolboxes\ND_ConfigFiles"}. Use CycleGeneric.xml for bicycle routing, DriveGeneric.xml for automobile routing regardless of spatial reference, or DriveMeters.xml for automobile routing in metres. _(**Note:**  If the spatial reference of the osm feature dataset has a linear unit of metres; it will result in faster routing performance. It will not work if linear unit is not metres)_.
4. *Output Network Dataset:* This field will auto-populate after the first parameter is filled in, and is the name of the network dataset that will be created.

After running this tool, the OSM feature dataset will be transformed into a Network dataset. All the functionality available for ArcGIS Network Datasets can be used with the resulting network dataset. The new network dataset will also include feature classes for barriers, turns, junctions, and roads. After generating the network dataset, the ArcGIS Network Analyst extension tools can be used to work with the dataset. The OSM-specific tools in the OpenStreetMap Toolbox can be used on the source data, but not on the resulting network dataset.
