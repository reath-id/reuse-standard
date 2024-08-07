---
title: Asset Type
description: Describes the type of physical asset (e.g. packaging) that is moving through the reuse cycle(s).
---

# Asset Type

Describes the type of physical asset (e.g. packaging) that is moving through the reuse cycle(s).

## Summary

There will be individual assets of the same "type", for example many individual bottles of type "Aluminium Bottle". The "asset type" describes all the (relevant) properties that are the same for each individual item.


## Fields

### Asset Type

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
asset_type_id|UUID|Yes|Unique identifier|
name|String|No|Descriptive name|
cycle_id|Array|Yes|Reference to one or more [reuse cycles](./3_3_Cycle.md) that this asset type moves through|
sku|String|No|Product SKU (should match [org](./3_2_Org.md)'s inventory records)|
reusable_asset_type|List|Yes|Single value from ["Packaging Type" codelist](./../4_Code_Lists/4_1_Code_Lists.md#packaging-types)|
product_category|List|No|What category would the overall product fall into? (e.g. for packaging this is overall category the consumable product be sold in). Single value from [GS1 GPC - Family Code](https://www.gs1.org/services/gpc-browser)|
industry|List|No|What industry is the asset servicing? Single value from [ICB Supersector codelist](https://www.ftserussell.com/data/industry-classification-benchmark-icb)|
unit_cost|Object|No|Cost per unit of the asset type, as a [money](./../2_Technical_Definitions/2_1_Technical_Definitions.md#money) object|
weight|Number|No|Weight of the empty asset (in grams)|
volume|Number|No|The volume of the asset (in mililitres)|
max_height|Number|No|The maximum height of the asset (in centimetres)|
max_width|Number|No|The maximum width of the asset (in centimetres)|
max_length|Number|No|The maximum length of the asset (in centimetres)|
tracker_type|List|No|The type of tracking attached to the asset to facilite matching to the digital records. Single value from ["Tracker Type" codelist](./../4_Code_Lists/4_1_Code_Lists.md#tracker-types)|
allergens|Array|No|Any known allergens contained or in contact with the asset. Array of values from ["allergens" codelist](./../4_Code_Lists/4_1_Code_Lists.md#allergens)|
certifications|String|No|Any relevant certification or manufacturing standard adhered to by the asset|
manufacturer|String|No|Name of supplier|
country_of_origin|List|Yes|Where the asset was manufactured. Single Country alpha-2 code from [ISO 3166-1:2020(en)](https://www.iso.org/obp/ui/#iso:std:iso:3166:-1:ed-4:v1:en)|
primary_material|List|Yes|What is majority of the asset made of? Single value from ["Materials" codelist](./../4_Code_Lists/4_1_Code_Lists.md#materials)|
primary_material_percentage|Number|No|What percentage of the asset is the majority material?|
auxiliary_material|List|No|The main material of an additional component, such as a bottle cap. Single value from ["Materials" codelist](./../4_Code_Lists/4_1_Code_Lists.md#materials)|
is_recycled|Boolean|Yes|Is the asset made from recycled material? (For environmental reporting)|
recycled_materials_percentage|Number|No|What % is made from recycled material? (For environmental reporting)|
recycled_materials_country_of_origin|List|No|Where the recycled material is sourced (for environmental reporting). Single Country alpha-2 code from [ISO 3166-1:2020(en)](https://www.iso.org/obp/ui/#iso:std:iso:3166:-1:ed-4:v1:en), see list [here](https://en.wikipedia.org/wiki/List_of_ISO_3166_country_code)|
cleaning_method|List|Yes|What type of cleaning is needed for this asset? Single value from ["Cleaning methods" codelist](./../4_Code_Lists/4_1_Code_Lists.md#cleaning-methods)|
cleaning_agent|String|No|What surfactant is used when cleaning this asset? Publishers should share a codelist reference to promote consistency and clarity|
cleaning_time|Number|No|How long does the cleaning cycle take? (in minutes)|
cleaning_temperature|Number|No|What temperature is the asset cleaned at? (in Celsius)|


[Schema](./../schema/asset_type.schema.json)
