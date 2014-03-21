# jbinto/bikeways-geojson

## About

Converting City of Toronto Bikeways ESRI Shapefile to something usable.

Github supports rendering GeoJSON according to this post by a Github employee:
http://ben.balter.com/2013/06/26/how-to-convert-shapefiles-to-geojson-for-use-on-github/

**UPDATE:** The file is too complex/big for Github to parse. It spins for about 30 seconds and times out. Will need to look into how to split it up into more manageable pieces. Likely means getting my hands dirty with PostGIS.

It's 50MB so I had to make a separate repository for this one file.

## Details

The shapefile from the city is dated March 1, 2014. I used the WGS84 file (see sources) using the following command: 

```bash
ogr2ogr -f GeoJSON -t_srs crs:84 bikeways.geojson CENTRELINE_BIKEWAY_OD_WGS84.shp
```


## Source


* [Open Data - Bikeways](http://www1.toronto.ca/wps/portal/contentonly?vgnextoid=9ecd5f9cd70bb210VgnVCM1000003dd60f89RCRD&vgnextchannel=1a66e03bb8d1e310VgnVCM10000071d60f89RCRD)

* [Bikeways WGS84 ESRI shapefile (zip)](http://opendata.toronto.ca/gcc/bikeways_wgs84.zip)

* [Bikeways MTM 3 Degree Zone 10 NAD27 (zip)](http://opendata.toronto.ca/gcc/bikeways_mtm3.zip)
