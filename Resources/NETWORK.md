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

Input OSM Feature Dataset: Browse to your OSM Feature Dataset.
Network Configuration File: The Network Configuration File defines the rules for generating your network dataset from the OSM data. The way you will use your network will determine which config file you use - and how you might want to adjust it to better suit your needs. For example, a riverbank can be a barrier if you’re defining a road network, or it can be a thoroughfare if you’re doing ship navigation. There is no automatic way to set these rules, but the OpenStreetMap toolbox contains network configuration sample files you can use to get started. Alternatively, if you want to generate a configuration file from scratch, see Generate a custom Network Configuration File Script. When you're first getting familiar with this tool, we recommend you use the configuration file that come with the OpenStreetMap toolbox. Browse to them from this Network Configuration File field in the tool dialog:{"\ArcGIS\Desktop10.1\ArcToolbox\Toolboxes\ND_ConfigFiles"} Which file you use depends on your use case - use CycleGeneric.xml for bicycle routing, DriveGeneric.xml for automobile routing regardless of spatial reference, or DriveMeters.xml for automobile routing in meters (e.g., NOTE: if the spatial reference of your osm feature dataset has a linear unit of meters; will result in faster routing performance. Will not work if linear unit is not meters).
Output Network Dataset: This field will auto-populate after the first parameter is filled in, and is the name of the network dataset that will be created.
Important: After running this tool, your OSM feature dataset will be transformed into a Network dataset. You will be able to use all the functionality available for ArcGIS Network Datasets with your resulting network dataset. Your new network dataset will also include feature classes for barriers, turns, junctions, and roads. After generating the network dataset, you can use the ArcGIS Network Analyst extension tools to work with the dataset. The OSM-specific tools in the OpenStreetMap Toolbox can be used on your source data, but not on the resulting network dataset.
