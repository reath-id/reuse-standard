---
title: Passport
description: Describes the state of all individual reusable assets at specific point in time.
---

# Passport

Describes the state of all individual reusable assets at specific point in time.

## Fields

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
asset_id|UUID|Yes|Unique identifier|
asset_type|UUID|Yes|Single [asset_type_id](./3_4_Asset_Type.md) for this asset|
in_reuse|Boolean|Yes|Is the asset live (within date_range), or has it been decommissioned?|
latest_activity|UUID|No|Single activity_id for the most recent (within date_range) activity in reuse cycle that this individual asset passed through|
latest_activity_date|DateTime|No|When most recent activity (within date_range) was tracked|
latest_activity_location|Object|No|[Location](./3_6_Passport_History.md#location) object of the most recent activity (within date_range)|
completed_cycle_count|Number|No|Count of the number of times (within date_range) this individual asset has completed the reuse cycle|
other_ref|String|No|Does the asset hold any additional referencing? i.e. batch code, expiration date etc|
decommission_reason|String|No|If the asset has been decommissioned, why?|


[Schema](./../schema/passport.schema.json)