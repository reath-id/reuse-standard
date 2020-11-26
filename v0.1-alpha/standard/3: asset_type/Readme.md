# Asset Type

Describes the type of physical asset (e.g. packaging) that is moving through the reuse cycle(s).

## Summary

There will be individual assets of the same "type", for example many individual bottles of type "Aluminium Bottle". The "asset type" describes all the (relevant) properties that are the same for each individual item.


## Fields

### Asset Type

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
|asset_type_id|UUID|Yes|Unique identifier|
|name|String|No|Descriptive name|
|cycle_id|UUID|Yes|Reference to the reuse cycle that this asset type moves through|
|sku|String|No|Product SKU (should match org's inventory records)|
|packaging_type|List|No|Single value from "Packaging Type" codelist|
|product_c_ategory|xxx|No|**TODO**: clarify|
|industry|String|No|**TODO**: clarify|
|unit_cost|Object|No|Cost per unit of the asset type, as a `money` object|
|weight|Decimal|No|Weight of the empty asset (in grams)|
|volume|Decimal|No|The volume of the asset (in mililitres)|
|max_height|Decimal|No|The maximum height of the asset (in centimetres)|
|max_width|Decimal|No|The maximum width of the asset (in centimetres)|
|max_length|Decimal|No|The maximum length of the asset (in centimetres)|
|tracker_type|List|No|The type of tracking attached to the asset to facilite matching to the digital records. Single value from "Tracker Type" codelist|
|allergens|xxx|No|**TODO**: clarify|
|certifications|String|No|Any relevant certification or manufacturing standard adhered to by the asset|
|manufacturer|String|No|Name of supplier|
|country_of_origin|List|Yes|Where the asset was manufactured. Single Country code from [ISO 3166-1:2020(en)](https://www.iso.org/obp/ui/#iso:std:iso:3166:-1:ed-4:v1:en)|
|primary_material|List|Yes|**TODO**: clarify. What is majority of the asset made of?|
|primary_material_percentage|Decimal|No|What percentage of the asset is the majority material?|
|auxiliary_material|List|Yes|**TODO**: clarify. The main material of an additional component, such as a bottle cap.|
|is_recycled|Boolean|Yes|Is the asset made from recycled material? (For environmental reporting)|
|recycled_materials_percentage|Decimal|No|What % is made from recycled material? (For environmental reporting)|
|recycled_materials_country_of_origin|List|No|Where the recycled material is sourced (for environmental reporting). Single Country code from [ISO 3166-1:2020(en)](https://www.iso.org/obp/ui/#iso:std:iso:3166:-1:ed-4:v1:en)|
|cleaning_method|List|Yes|**TODO**: clarify. What type of cleaning is needed for this asset? i.e. Washing, UV etc|
|cleaning_agent|List|Yes|**TODO**: clarify. What surfactant is used when cleaning this asset?|
|cleaning_time|Decimal|No|How long does the cleaning cycle take? (in minutes)|
|cleaning_temperature|Decimal|No|What temperature is the asset cleaned at? (in Celsius)|

### Money

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
|currency|List|Yes|Currency symbol from |
|amount|Decimal|Yes|Value amount|
