## Layer files

The zip file contains layer files based on the OSM Humanitarian CartoCSS style.

The layers are designed to be used with data loaded using the ArcGIS OpenStreetMap Editor tools.

In addition to the standard tags extracted by the tools the following tags should also be added:

- name
- name:en
- ref
- oneway
- maritime
- admin_level
- seasonal
- tunnel
- bridge
- office
- religion
- craft
- pump
- content
- drinking_water
- tower:type
- emergency
- ford
- generator:source

There are a number of definition queries set on the layers and in order to speed up drawing it is recommended to build an attribute index for each of the tags.

The land layer utilises at the [osm_land_polygons](http://openstreetmapdata.com/data/land-polygons).

The bathymetry layer utilises the [Natural Earth bathymetry polygons](http://www.naturalearthdata.com/downloads/10m-physical-vectors/10m-bathymetry). Select [download all](http://www.naturalearthdata.com/http//www.naturalearthdata.com/download/10m/physical/ne_10m_bathymetry_all.zip) and unzip.
