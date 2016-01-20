##OpenStreetMap for ArcGIS
![OSM](https://raw.githubusercontent.com/GASCUK/OpenStreetMap-ArcGIS/master/Images/osm_screenshot.png)

##Introduction

This repository provides a means to style OpenStreetMap data imported into ArcGIS using the [OpenStreetMap Editor for ArcGIS](http://www.esri.com/software/arcgis/extensions/openstreetmap).

The stylesheet and layers included in the repository have been designed to simplify the process of symbolising and displaying OSM data. The style design is based on the [OpenStreetMap](http://openstreetmap.org/) humanitarian theme. The original style information can be found at [HDM-CartoCSS](https://github.com/hotosm/HDM-CartoCSS) and is derived from [CartoCSS](https://github.com/mapbox/carto).

##Description

The style file contains symbols for four distinct scale levels. Each zoom level groups one or more of the display levels from OpenStreetMap.

- Zoom 1: levels 0-10
- Zoom 2: levels 11-12
- Zoom 3: levels 13-15
- Zoom 4: levels 16-19

The following images are examples of how the layers look. There have been a number of changes to the layers that will be reflected in future updates.


These styles are a work in progress and layer files will produced for each zoom level in the ArcGIS online tiling scheme. Each level will show the required features based on the HDM-CartoCSS style and additional features not included.

##License

The following copyrights should be noted and referenced when creating any maps utilising these styles:

- Stylesheet is licenced under CCO.
- Nori icons are licenced under CCO.
- Maki icons are © [MapBox](https://www.mapbox.com/maki/).
