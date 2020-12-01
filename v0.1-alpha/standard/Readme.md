# Structure


## Fields

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
[org](./1:%20org)|Object|Yes|The single organisation responsible for this reuse dataset
date|DateTime|Yes|When this data was compiled
[cycles](./2:%20cycle)|Array|Yes|Defines the reuse cycle(s). Array of [cycle objects](./2:%20cycle)
[asset_types](./3:%20asset_type)|Array|No|Describes the types of physical reusable assets (eg packaging) that are moving through the reuse cycles. Array of [asset_type objects](./3:%20asset_type). *Required if either passport or passport_history fields are present*
date_range|Object|No|Optional date range for the Passport and Passport History data, as a [Date Range](./#Date%20Range) object. *Required if passport_history is present*
[passports](./4:%20passport)|Array|No|Describes the state of all individual reusuable assets at specific point in time (either date_range end or date). Array of [passport objects](./4:%20passport)
[passport_history](./5:%20passport_history)|Array|No|Record of all Activities of a reuse cycle that each individual reusuable asset has been through, within date_range start and end dates. Array of [passport_history objects](./5:%20passport_history)


## Date Range

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
start|DateTime|Yes|When the date range starts
end|DateTime|Yes|When the date range ends
