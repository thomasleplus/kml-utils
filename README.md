# KML utilities

Utilities for KML files

## Scripts

### find-kml-shortest-path

Finds the shortest path to visit all placemarks in a KML file using the traveling salesman approach. Uses nearest neighbor heuristic followed by 2-opt optimization to minimize total distance. Outputs a new KML file with a LineString showing the optimized route.

### find-kml-clusters

Finds the highest-value clusters of placemarks in a KML file ("most bang for your buck"). Groups placemarks into walkable clusters (connected components whose members are within `--epsilon` metres of a neighbour), computes an optimized walking route per cluster (nearest neighbour heuristic followed by 2-opt),
keeps clusters worth at least `--min-points` total whose route length falls within `[--min-dist, --max-dist]` metres, ranks the survivors by points per kilometre, and outputs a new KML file with one folder per cluster (its placemarks plus a LineString showing the route).
A per-placemark point value is read with the optional `--points-pattern` regular expression (one capture group), falling back to `--default-points` when no pattern is given or a placemark does not match.

Usage: `find-kml-clusters --epsilon M --min-points P --min-dist M --max-dist M [--points-pattern RE] [--default-points N] file.kml`

### find-kml-duplicates

Finds duplicate placemarks within a KML file that are within a specified radius of each other. Groups together all placemarks that are within the given radius (default 1 km) and reports them as duplicates. Useful for identifying redundant location markers.

Usage: `find-kml-duplicates [-r radius] file.kml`

### find-kml-uniques

Compares two KML files and finds placemarks in the first file that don't have any matches within a specified radius (default 1 km) in the second file. Useful for finding locations that are unique to the first file.

Usage: `find-kml-uniques [-r radius] file1.kml file2.kml`

### find-kml-min-distances

Analyzes a KML file and for each placemark, finds its nearest neighbor and reports the distance between them in kilometers. Useful for understanding the density and spacing of placemarks.

Usage: `find-kml-min-distances file.kml`

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## Security

Please read [SECURITY.md](SECURITY.md) for details on our security policy and how to report security vulnerabilities.

## Code of Conduct

Please read [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for details on our code of conduct.

## License

This project is licensed under the terms of the [LICENSE](LICENSE) file.
