# 2018-US-Midterm-Elections

This GitHub repository seeks to expand on the work of [John Johnson](https://johndjohnson.info/about/) by making his Wisconsin 2018 midterm election results data and geographical boundaries available to the general public.

## Wisconsin 2018 Reporting Units
When voters in the state of Wisconsin cast ballots for national and state elections, they do so at the "ward"-level, an administrative boundary created to conduct elections. Yet when it comes to tabulating and reporting election results, Wisconsin officials combine wards into "reporting units", larger administrative boundaries comprised of one or more wards. There are many reasons Wisconsin election officials do this, chief among them is to protect the anonymity of voters who live in sparsely populated areas in Wisconsin<sup id="a1">[[1]](#f1)</sup>.

The composition of wards comprising reporting units change with each election. This means comparing Wisconsin election results over time is a tediously difficult undertaking, requiring analysts to decompose the makeup of reporting units for each election. Moreover, there is no authoritative body that produces shapefiles for reporting unit boundaries, leaving analysts, journalists, and the public little opportunity to visualize Wisconsin election results in any meaningful way.

For the 2018 midterm elections, John Johnson, Research Fellow at the Marquette Law School, has filled in that gap and created a [shapefile that provides high-quality, consistent boundaries and election results for Wisconsin](https://johndjohnson.info/2018/12/10/a-shapefile-of-wisconsin-november-2018-reporting-units/). 

### Transforming the Shapefiles to geojson
Using [mapshaper](https://mapshaper.org/), we converted John Johnson's reporting units shapefile into geojson format. The shapefile itself contains lower-level features that make the resulting file quite large. We used [mapshaper's command line tools](https://github.com/mbloch/mapshaper/wiki/Command-Reference) to simplify the features by employing the Visvalingam simplification method, which 

> iteratively removes the least important point from a polyline. The importance of points is measured using a metric based on the geometry of the triangle formed by each non-endpoint vertex and the two neighboring vertices.

We applied the following command to simplify John Johnson's features to 10% of original size:

```
-simplify 10%
```

### Using Mapbox Studio to Create Tilsets and Style Maps
We then converted the geojson into a tileset using [Mapbox Studio](https://www.mapbox.com/studio). Though we simplified the original shapefile to produce a smaller geojson file, we applied only standard transformations from geojson to Mapbox-compliant tilesets. We created a new map style in Mapbox Studio by selecting a "Basic Template" and adding the newly-transformed Wisconsin reporting units layer to that style.

Mapbox Studio provides functions that allow a user to style layers on a map in almost infinite varieties. Web features like transitions, opacities, color scales, etc., can be modified to create unique maps that possess beautiful qualities and create exquisite user experiences.

<b id="f1">1</b> For a more in-depth understanding of how Wisconsin officials administer elections, refer to the "WARDS, DISTRICTS, REPORTING UNITS & ANNEXATIONS" [publication](https://elections.wi.gov/sites/default/files/publication/65/ea_wards_districts_reporting_units_annexations_f_18339.pdf) produced by the Wisconsin Elections Commission. <br/>