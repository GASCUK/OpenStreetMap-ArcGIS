##Introduction

Provides a means to style OpenStreetMap data imported into ArcGIS using the [OpenStreetMap Editor for ArcGIS](http://www.esri.com/software/arcgis/extensions/openstreetmap).

The styles are based on the humanitarian theme from [OpenStreetMap](http://openstreetmap.org/). The original style information is from [HDM-CartoCSS](https://github.com/hotosm/HDM-CartoCSS) and is based on [CartoCSS](https://github.com/mapbox/carto).

It should be noted that it is not recmmended to load large areas using these tools. A recent test on the whole of Africa took approximately 7 days to load all the data and create a network dataset. Additionally the layer files have not yet been optomised and can be slow to draw with large amounts of data.

The use of attribute indexes should be considered to speed up the layer drawing.

In addition to the styles a work flow will be generated that will walk through a complete process of:

Load

Extract additional tags

Build network dataset

Add Attribute Indexes

Update template mxd with loaded data

Publish to ArcGIS server

Generate tile cache

In addition address locators will be built and published along with publishing the network dataset. The entire process will be semi automated using geoprocessing scripts.

##Description

The style file contains symbols for 4 distinct scale levels. Each zoom level groups 1 or more of the display levels from OpenStreetMap. The following images are examples of how the layers look. There have been a number of changes to the layers that will be reflected in future updates. The drawing order of roads has been fixed so that roads do not terminate in the centre of other symbols.

These styles are a work in progress and layer files will produced for each zoom level in the ArcGIS online tiling scheme. Each level will show the required features based on the HDM-CartoCSS style and additional features not included.

##License

The following copyrights should be noted and referenced when creating any maps utilising these styles:

- Stylesheet is licenced under CCO.
- Nori icons are licenced under CCO.
- Maki icons are © [MapBox](https://www.mapbox.com/maki/).
