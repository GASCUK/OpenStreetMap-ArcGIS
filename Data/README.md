##OpenStreetMap for ArcGIS
![OSM](https://raw.githubusercontent.com/GASCUK/OpenStreetMap-ArcGIS/master/Images/osm_banner.png)

##Introduction

This repository provides a means to style OpenStreetMap data imported into ArcGIS using the [OpenStreetMap Editor for ArcGIS](http://www.esri.com/software/arcgis/extensions/openstreetmap).

The stylesheet and layers included in the repository have been designed to simplify the process of symbolising and displaying OSM data. The style design is based on the [OpenStreetMap](http://openstreetmap.org/) humanitarian theme. The original style information can be found at [HDM-CartoCSS](https://github.com/hotosm/HDM-CartoCSS) and is derived from [CartoCSS](https://github.com/mapbox/carto).

##Description

The style file contains symbols for four distinct scale levels. Each zoom level groups one or more of the display levels from OpenStreetMap:

1. Display levels 0-10
2. Display levels 11-12
3. Display levels 13-15
4. Display levels 16-19

Each layer file contains specific points, lines and polygon features to be displayed at each level. This information was drawn from the CartoCSS MSS files for the OSM humanitarian theme. The features displayed at each level draw their symbology from the stylesheet created based on the Nori and Maki icons, designed to look as similiar to the OSM humanitarian symbols as possible.

**_Note:_** *There are currently no labels included in the template as the speed that the layers take to display is currently being tested. In future, country and captial city labels may be included but more detailed labelling such as rivers and roads will probably not be added*

## Workflow

The stylesheet, the layer files, raw OSM data and the ArcGIS OSM toolbox are required to be able to display OSM data within ArcGIS in the style of the humanitarian theme. See [WORKFLOW.md](https://github.com/GASCUK/OpenStreetMap-ArcGIS/blob/master/WORKFLOW.md) for more information.

## Maintainers

- GASC [@gascuk](https://github.com/gascuk)
- Dave Barrett [@daveb1034](https://github.com/daveb1034)
- Rachel Munslow [@rmunslow](https://github.com/rmunslow)

##License

The following copyrights should be noted and referenced when creating any maps utilising these styles:

- Stylesheet is licenced under CCO.
- Nori icons are licenced under CCO.
- Maki icons are © [MapBox](https://www.mapbox.com/maki/).
