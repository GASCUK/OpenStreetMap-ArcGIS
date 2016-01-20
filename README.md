##OpenStreetMap for ArcGIS
![OSM](https://raw.githubusercontent.com/GASCUK/OpenStreetMap-ArcGIS/master/Images/osm.png)

##Introduction

Provides a means to style OpenStreetMap data imported into ArcGIS using the [OpenStreetMap Editor for ArcGIS](http://www.esri.com/software/arcgis/extensions/openstreetmap).

The styles are based on the humanitarian theme from [OpenStreetMap](http://openstreetmap.org/). The original style information is from [HDM-CartoCSS](https://github.com/hotosm/HDM-CartoCSS) and is based on [CartoCSS](https://github.com/mapbox/carto).

_**Note:** It should be noted that it is not recommended to load large areas using these tools. A recent test on the whole of Africa took approximately 7 days to load all the data and create a network dataset. Additionally the layer files have not yet been optimised and can be slow to draw with large amounts of data. The use of attribute indexes should be considered to speed up the layer drawing._

#####To do
This project is still in progress and there are a number of different areas that still need working on:
- [ ] Create a work flow that will walk through the complete process from loading the data to generating a tile cache.
- [ ] Generate labels at different zoom levels for country names and capital cities.

##Description

The style file contains symbols for four distinct scale levels. Each zoom level groups one or more of the display levels from OpenStreetMap.

- Zoom 1: levels 0-10
- Zoom 2: levels 11-12
- Zoom 3: levels 13-15
- Zoom 4: levels 16-19

The following images are examples of how the layers look. There have been a number of changes to the layers that will be reflected in future updates.

#####Level 3
![Level 3](https://raw.githubusercontent.com/GASCUK/OpenStreetMap-ArcGIS/master/Images/Zoom3.jpg)
#####Level 9
![Level 9](https://raw.githubusercontent.com/GASCUK/OpenStreetMap-ArcGIS/master/Images/Zoom9.jpg)
#####Level 12
![Level 12](https://raw.githubusercontent.com/GASCUK/OpenStreetMap-ArcGIS/master/Images/Zoom12.jpg)
#####Level 14
![Level 14](https://raw.githubusercontent.com/GASCUK/OpenStreetMap-ArcGIS/master/Images/Zoom14.jpg)
#####Level 16
![Level 16](https://raw.githubusercontent.com/GASCUK/OpenStreetMap-ArcGIS/master/Images/Zoom16.jpg)
#####Level 18
![Level 18](https://raw.githubusercontent.com/GASCUK/OpenStreetMap-ArcGIS/master/Images/Zoom18.jpg)


These styles are a work in progress and layer files will produced for each zoom level in the ArcGIS online tiling scheme. Each level will show the required features based on the HDM-CartoCSS style and additional features not included.

##License

The following copyrights should be noted and referenced when creating any maps utilising these styles:

- Stylesheet is licenced under CCO.
- Nori icons are licenced under CCO.
- Maki icons are © [MapBox](https://www.mapbox.com/maki/).
