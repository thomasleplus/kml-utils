# KML utilities

Utilities for KML files

## Scripts

### find-kml-shortest-path

Finds the shortest path to visit all placemarks in a KML file using the traveling salesman approach. Uses nearest neighbor heuristic followed by 2-opt optimization to minimize total distance. Outputs a new KML file with a LineString showing the optimized route.

### find-kml-duplicates

Finds duplicate placemarks within a KML file that are within a specified radius of each other. Groups together all placemarks that are within the given radius (default 1 km) and reports them as duplicates. Useful for identifying redundant location markers.

Usage: `find-kml-duplicates [-r radius] file.kml`

### find-kml-uniques

Compares two KML files and finds placemarks in the first file that don't have any matches within a specified radius (default 1 km) in the second file. Useful for finding locations that are unique to the first file.

Usage: `find-kml-uniques [-r radius] file1.kml file2.kml`

### find-kml-min-distances

Analyzes a KML file and for each placemark, finds its nearest neighbor and reports the distance between them in kilometers. Useful for understanding the density and spacing of placemarks.

Usage: `find-kml-min-distances file.kml`
