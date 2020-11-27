# reuse.id


## Fields

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
org|Object|Yes|The single organisation responsible for this resue dataset
date|DateTime|Yes|When this data was compiled
date_range_start|DateTime|No|Optional date from which the Passport data starts. *Required* if passport_history is present
date_range_end|DateTime|No|Optional date on which the Passport data ends. *Required* if passport_history is present
cycles|Array|Yes|Defines the reuse cycle(s). Array of [cycle objects](cycle/)
asset_types|Array|No|Describes the types of physical reusable assets (eg packaging) that are moving through the reuse cycles. *Required* if either passport or passport_history fields are present. Array of [asset_type objects](asset_type/)
passports|Array|No|Describes the state of all individual reusuable assets at specific point in time (ie date_range_end or date). Array of [passport objects](passport/)
passport_history|Array|No|Record of all Activities of a reuse cycle that each individual reusuable asset has been through between date_range_start and date_range_end
