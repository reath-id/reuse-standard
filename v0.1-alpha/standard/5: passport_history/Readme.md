# Passport

Record of all Activities of a reuse cycle that each individual reusuable asset has been through (within date_range).

## Fields

### Passport History

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
|asset|UUID|Yes|Single asset_id of the passport (i.e. individual asset)|
|activity|UUID|Yes|Single activity_id for the activity in reuse cycle that this individual asset passed through|
|date|DateTime|Yes|When activity was tracked|
|location|Object|No|Location where activity was tracked. This may be a geo location *and/or* business location (e.g. "wharehouse 1")|

### Location

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
location_name|String|No|Business location (e.g. "wharehouse 1")
coordinates|Array|No|[lon, lat] using the coordinate reference system as per [GeoJSON Open Standard](https://tools.ietf.org/html/rfc7946#page-12)