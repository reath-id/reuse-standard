# reuse.id


## Fields

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
org|Object|Yes|The single organisation responsible for this resue dataset
date|Date|Yes|When this data was compiled
date_range_start|Date|No|Optional date from which the Passport data starts. *Required* if and passport_history is present
date_range_end|Date|No|Optional date on which the Passport data ends
cycles|Array|Yes|Defines the reuse cycle(s)
asset_types|Array|No|Describes the types of physical reusable assets (eg packaging) that are moving through the reuse cycles *Required* if and Passport fields are present
passport_summary|Array|No|Describes the current state of all individual reusuable asset as at date_range_end (or date)
passport_history|Array|No|Record of all Activities that each individual reusuable asset has been through between date_range_start and date_range_end
