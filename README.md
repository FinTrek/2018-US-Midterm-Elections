# 2018-US-Midterm-Elections

## Wisconsin 2018 Reporting Units
Wisconsin election results are reported at the "reporting unit". These reporting units are generally comprised of one or more Wisconsin wards. Since many wards are sparsely populated, to protect the anonymity of voters, local election officials combine wards into reporting units.

Reporting units change each election; moreover, there is no government agency or instituion that produces shapefiles of these changes in boundaries. [John Johnson, Research Fellow at the Marquette Law School](https://johndjohnson.info/about/), has created a [shapefile that contains these Wisconsin "reporting units" for the 2018 midterm elections](https://johndjohnson.info/2018/12/10/a-shapefile-of-wisconsin-november-2018-reporting-units/).

### Transforming the Shapefiles to GeoJson and then to Mapbox Tileset
Using [mapshaper](https://mapshaper.org/), we converted John Johnson's reporting units shapefile into GeoJson format. Then, we converted the GeoJson into a tileset using [Mapbox Studio](https://www.mapbox.com/studio). We applied only standard transformations from shapefile to GeoJson to Mapbox-compliant tileset.

### Creating a Map Style in Mapbox Studio
We created a new map style in Mapbox Studio by selecting a "Basic Template" and adding the newly-transformed Wisconsin Reporting Units tileset to that style. The tileset has a zoom extent of 9 to 22. In other words, the polygon boundaries are only visible once a user zooms in to Wiscons past 9 [Ed: what are the units here?]