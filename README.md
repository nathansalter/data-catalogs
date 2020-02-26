# OpenActive Data Catalogs

OpenActive Data Catalogs provide a mechanism for registering [OpenActive Datasite Sites](https://developer.openactive.io/publishing-data/dataset-sites) so that they can be discovered and harvested by data users.


## Structure

The [OpenActive Data Catalog Collection](https://openactive.io/data-catalogs/data-catalog-collection.jsonld) contains a list of Data Catalogs, which each contain a list of Dataset Sites. Each Dataset Site references its OpenActive feed URLs within JSON-LD metadata.


## Processing guidance

1. Download the OpenActive Data Catalog Collection using a GET request to the canonical URL [`https://openactive.io/data-catalogs/data-catalog-collection.jsonld`](https://openactive.io/data-catalogs/data-catalog-collection.jsonld).

2. Download each Data Catalog referenced by the `hasPart` array in the OpenActive Data Catalog Collection.

3. Download each Dataset Site referenced by the `dataset` array in each Data Catalog ([Data Catalog example data](https://opendata.leisurecloud.live/api/datacatalog)).

4. Extract the JSON-LD metadata from inside the HTML page of the Dataset Site ([example extraction library](https://www.npmjs.com/package/htmlmetaparser), [Dataset Site example](https://opendata.fusion-lifestyle.com/OpenActive/)).

5. The feed URLs are located in the `distribution` property of the JSON-LD metadata within the Dataset Site.


## Hosted data files

The following two data files are hosted from within [this repository](https://github.com/openactive/data-catalogs/). They should be accessed via the canonical URLs below:

### OpenActive Data Catalog Collection
A collection of all Data Catalogs recognised as compliant by OpenActive.

[`https://openactive.io/data-catalogs/data-catalog-collection.jsonld`](https://openactive.io/data-catalogs/data-catalog-collection.jsonld)

### OpenActive Data Catalog for Singular Datasets
A Data Catalog for singular datasets that are not included in other Data Catalogs. This data catalog is included in the OpenActive Data Catalog Collection.

[`https://openactive.io/data-catalogs/singular.jsonld`](https://openactive.io/data-catalogs/singular.jsonld)


## Related specifications

The Dataset Site JSON-LD metadata format, Data Catalog format, and Data Catalog Collection format are planned to be standardised as part of the [Dataset API Discovery specification](https://www.openactive.io/dataset-api-discovery/EditorsDraft/).
