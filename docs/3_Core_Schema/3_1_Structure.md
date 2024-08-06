# Structure

## Fields

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
[org](./3_2_Org.md)|Object|Yes|The single organisation responsible for this reuse dataset
date|DateTime|Yes|When this data was compiled
[cycles](./3_3_Cycle.md)|Array|Yes|Defines the reuse cycle(s). Array of [cycle objects](./3_3_Cycle.md)
[asset_types](./3_4_Asset_Type.md)|Array|No|Describes the types of physical reusable assets (eg packaging) that are moving through the reuse cycles. Array of [asset_type objects](./3_4_Asset_Type.md). *Required if either passport or passport_history fields are present*
date_range|Object|No|Optional date range for the Passport and Passport History data, as a [Date Range](./../2_Technical_Definitions/2_1_Technical_Definitions.md#date-range) object. *Required if passport_history is present*
[passports](./3_5_Passport.md)|Array|No|Describes the state of all individual reusable assets at specific point in time (either date_range end or date). Array of [passport objects](./3_5_Passport.md)
[passport_history](./3_6_Passport_History.md)|Array|No|Record of all Activities of a reuse cycle that each individual reusable asset has been through, within date_range start and end dates. Array of [passport_history objects](./3_6_Passport_History.md)

[Schema](./../schema/reuse.schema.json)

## Examples

Some fictional examples:

=== "Reuse cycle only"
    ``` JSON
    {
        "$schema": "https://reuse-standard.org/schema/reuse.schema.json#",
        "org": {
            "name": "Endzone.io Ltd t/a HappyPorch",
            "org_id": "GB-COH-SC492581"
        },
        "date": "2020-12-01T18:25:43.511Z",
        "cycles": [
            {
                "cycle_id": "7b7628a8-09a6-4913-bbb6-67e2ef19aed2",
                "reuse_model": "return_home",
                "activities": [
                    {
                        "activity_id": "ecfcfa57-89fd-48ee-aaa8-6b74ddcd59cb",
                        "activity_type": "start_step",
                        "name": "Filled",
                        "next" : ["1028b545-b5f5-4e3c-9dbc-64561ce91f1b"]
                    },
                    {
                        "activity_id": "1028b545-b5f5-4e3c-9dbc-64561ce91f1b",
                        "activity_type": "step",
                        "name": "Delivered",
                        "next" : ["5d207fc1-761e-4c1b-baf3-75e6ffbf7f1f"]
                    },
                    {
                        "activity_id": "5d207fc1-761e-4c1b-baf3-75e6ffbf7f1f",
                        "activity_type": "step",
                        "name": "Returned",
                        "next" : ["d922c237-7041-4c01-8272-161941698900"]
                    },
                    {
                        "activity_id": "d922c237-7041-4c01-8272-161941698900",
                        "activity_type": "clean_step",
                        "name": "Cleaned",
                        "next" : ["ecfcfa57-89fd-48ee-aaa8-6b74ddcd59cb"]
                    }
                ]
            }
        ]
    }
    ```
=== "Reuse cycle with entry and exit"
    ``` JSON
    {
        "$schema": "https://reuse-standard.org/schema/reuse.schema.json#",
        "org": {
            "name": "Endzone.io Ltd t/a HappyPorch",
            "org_id": "GB-COH-SC492581"
        },
        "date": "2020-12-01T18:25:43.511Z",
        "cycles": [
            {
                "cycle_id": "39d843ac-2e6c-46c5-8e43-249066d5d059",
                "reuse_model": "refill_go",
                "activities": [
                    {
                        "activity_id": "1a774e5a-cd1a-40d4-97b7-f513fd4112b3",
                        "activity_type": "step",
                        "name": "Purchased",
                        "next" : ["a2cc56d3-1223-4bca-bc21-f0a35109d166"]
                    },
                    {
                        "activity_id": "a2cc56d3-1223-4bca-bc21-f0a35109d166",
                        "activity_type": "start_step",
                        "name": "Filled",
                        "next" : ["acc46828-10cd-4066-8700-011dc35df8ff"]
                    },
                    {
                        "activity_id": "acc46828-10cd-4066-8700-011dc35df8ff",
                        "activity_type": "step",
                        "name": "Delivered",
                        "next" : ["2b91eb48-b33f-400b-9b54-88b338f2cb9d"]
                    },
                    {
                        "activity_id": "2b91eb48-b33f-400b-9b54-88b338f2cb9d",
                        "activity_type": "step",
                        "name": "Returned",
                        "next" : ["441ed3d0-cfac-48d9-a9ef-571594d8e400"]
                    },
                    {
                        "activity_id": "441ed3d0-cfac-48d9-a9ef-571594d8e400",
                        "activity_type": "clean_step",
                        "name": "Cleaned",
                        "next" : ["a2cc56d3-1223-4bca-bc21-f0a35109d166", "bfe19346-5463-4f4c-83a7-88ba0f1e5531"]
                    },
                    {
                        "activity_id": "bfe19346-5463-4f4c-83a7-88ba0f1e5531",
                        "activity_type": "step",
                        "name": "Recycled"
                    }
                ]
            }
        ]
    }
    ```
=== "Reuse cycle with asset types"
    ``` JSON
    {
        "$schema": "https://reuse-standard.org/schema/reuse.schema.json#",
        "org": {
            "name": "Endzone.io Ltd t/a HappyPorch",
            "org_id": "GB-COH-SC492581"
        },
        "date": "2020-12-01T19:25:43.511Z",
        "cycles": [
            {
                "cycle_id": "7b7628a8-09a6-4913-bbb6-67e2ef19aed2",
                "reuse_model": "return_home",
                "activities": [
                    {
                        "activity_id": "ecfcfa57-89fd-48ee-aaa8-6b74ddcd59cb",
                        "activity_type": "start_step",
                        "name": "Filled",
                        "next" : ["1028b545-b5f5-4e3c-9dbc-64561ce91f1b"]
                    },
                    {
                        "activity_id": "1028b545-b5f5-4e3c-9dbc-64561ce91f1b",
                        "activity_type": "step",
                        "name": "Delivered",
                        "next" : ["5d207fc1-761e-4c1b-baf3-75e6ffbf7f1f"]
                    },
                    {
                        "activity_id": "5d207fc1-761e-4c1b-baf3-75e6ffbf7f1f",
                        "activity_type": "step",
                        "name": "Returned",
                        "next" : ["d922c237-7041-4c01-8272-161941698900"]
                    },
                    {
                        "activity_id": "d922c237-7041-4c01-8272-161941698900",
                        "activity_type": "clean_step",
                        "name": "Cleaned",
                        "next" : ["ecfcfa57-89fd-48ee-aaa8-6b74ddcd59cb"]
                    }
                ]
            }
        ],
        "asset_types": [
            {
                "asset_type_id": "b88db315-0e61-489a-be89-9e4a6fa62eb4",
                "name": "bottle",
                "cycle_id": ["7b7628a8-09a6-4913-bbb6-67e2ef19aed2"],
                "reusable_asset_type": "bottle",
                "unit_cost": {
                    "currency": "GBP",
                    "value": "22.22"
                },
                "country_of_origin": "GB",
                "primary_material": "glass",
                "auxiliary_material": "plastic",
                "is_recycled": "false",
                "cleaning_method": "washing"
            }
        ]
    }
    ```
=== "Reuse cycle with asset types and passports"
    ``` JSON
    {
        "$schema": "https://reuse-standard.org/schema/reuse.schema.json#",
        "org": {
            "name": "Endzone.io Ltd t/a HappyPorch",
            "org_id": "GB-COH-SC492581"
        },
        "date": "2020-12-01T19:25:43.511Z",
        "cycles": [
            {
                "cycle_id": "7b7628a8-09a6-4913-bbb6-67e2ef19aed2",
                "reuse_model": "return_home",
                "activities": [
                    {
                        "activity_id": "ecfcfa57-89fd-48ee-aaa8-6b74ddcd59cb",
                        "activity_type": "start_step",
                        "name": "Filled",
                        "next" : ["1028b545-b5f5-4e3c-9dbc-64561ce91f1b"]
                    },
                    {
                        "activity_id": "1028b545-b5f5-4e3c-9dbc-64561ce91f1b",
                        "activity_type": "step",
                        "name": "Delivered",
                        "next" : ["5d207fc1-761e-4c1b-baf3-75e6ffbf7f1f"]
                    },
                    {
                        "activity_id": "5d207fc1-761e-4c1b-baf3-75e6ffbf7f1f",
                        "activity_type": "step",
                        "name": "Returned",
                        "next" : ["d922c237-7041-4c01-8272-161941698900"]
                    },
                    {
                        "activity_id": "d922c237-7041-4c01-8272-161941698900",
                        "activity_type": "clean_step",
                        "name": "Cleaned",
                        "next" : ["ecfcfa57-89fd-48ee-aaa8-6b74ddcd59cb"]
                    }
                ]
            }
        ],
        "asset_types": [
            {
                "asset_type_id": "b88db315-0e61-489a-be89-9e4a6fa62eb4",
                "name": "bottle",
                "cycle_id": ["7b7628a8-09a6-4913-bbb6-67e2ef19aed2"],
                "reusable_asset_type": "bottle",
                "unit_cost": {
                    "currency": "GBP",
                    "value": "22.22"
                },
                "country_of_origin": "GB",
                "primary_material": "glass",
                "auxiliary_material": "plastic",
                "is_recycled": "false",
                "cleaning_method": "washing"
            }
        ],
        "date_range": {
            "start": "2020-01-01T00:00:00.000Z",
            "end": "2020-12-01T19:25:43.511Z"
        },
        "passports": [
            {
                "asset_id": "1598910f-0981-4065-96a8-6e7a0ff4fac4",
                "in_reuse": true
            },
            {
                "asset_id": "9a29c6a6-10ad-4c25-a5bf-1dfac59aa675",
                "in_reuse": true,
                "latest_activity": "ecfcfa57-89fd-48ee-aaa8-6b74ddcd59cb",
                "latest_activity_date": "2020-11-01T19:11:34.111Z",
                "latest_activity_location": {
                    "name": "warehouse 1"
                },
                "completed_cycle_count": 2
            },
            {
                "asset_id": "f4ae39f9-2688-4056-b65c-5841a30b9e7d",
                "in_reuse": true,
                "latest_activity": "5d207fc1-761e-4c1b-baf3-75e6ffbf7f1f",
                "latest_activity_date": "2020-10-01T07:11:34.111Z",
                "latest_activity_location": {
                    "name": "retail 1"
                },
                "completed_cycle_count": 6
            }
        ]
    }
    ```
=== "Reuse cycle with asset types and passport history"
    ``` JSON
    {
        "$schema": "https://reuse-standard.org/schema/reuse.schema.json#",
        "org": {
            "name": "Endzone.io Ltd t/a HappyPorch",
            "org_id": "GB-COH-SC492581"
        },
        "date": "2020-12-01T19:25:43.511Z",
        "cycles": [
            {
                "cycle_id": "7b7628a8-09a6-4913-bbb6-67e2ef19aed2",
                "reuse_model": "return_home",
                "activities": [
                    {
                        "activity_id": "ecfcfa57-89fd-48ee-aaa8-6b74ddcd59cb",
                        "activity_type": "start_step",
                        "name": "Filled",
                        "next" : ["1028b545-b5f5-4e3c-9dbc-64561ce91f1b"]
                    },
                    {
                        "activity_id": "1028b545-b5f5-4e3c-9dbc-64561ce91f1b",
                        "activity_type": "step",
                        "name": "Delivered",
                        "next" : ["5d207fc1-761e-4c1b-baf3-75e6ffbf7f1f"]
                    },
                    {
                        "activity_id": "5d207fc1-761e-4c1b-baf3-75e6ffbf7f1f",
                        "activity_type": "step",
                        "name": "Returned",
                        "next" : ["d922c237-7041-4c01-8272-161941698900"]
                    },
                    {
                        "activity_id": "d922c237-7041-4c01-8272-161941698900",
                        "activity_type": "clean_step",
                        "name": "Cleaned",
                        "next" : ["ecfcfa57-89fd-48ee-aaa8-6b74ddcd59cb"]
                    }
                ]
            }
        ],
        "asset_types": [
            {
                "asset_type_id": "b88db315-0e61-489a-be89-9e4a6fa62eb4",
                "name": "bottle",
                "cycle_id": ["7b7628a8-09a6-4913-bbb6-67e2ef19aed2"],
                "reusable_asset_type": "bottle",
                "unit_cost": {
                    "currency": "GBP",
                    "value": "22.22"
                },
                "country_of_origin": "GB",
                "primary_material": "glass",
                "auxiliary_material": "plastic",
                "is_recycled": "false",
                "cleaning_method": "washing"
            }
        ],
        "date_range": {
            "start": "2020-01-01T00:00:00.000Z",
            "end": "2020-12-01T19:25:43.511Z"
        },
        "passports": [
            {
                "asset_id": "1598910f-0981-4065-96a8-6e7a0ff4fac4",
                "in_reuse": true
            },
            {
                "asset_id": "9a29c6a6-10ad-4c25-a5bf-1dfac59aa675",
                "in_reuse": true,
                "latest_activity": "ecfcfa57-89fd-48ee-aaa8-6b74ddcd59cb",
                "latest_activity_date": "2020-11-01T19:11:34.111Z",
                "latest_activity_location": {
                    "name": "warehouse 1"
                },
                "completed_cycle_count": 2
            },
            {
                "asset_id": "f4ae39f9-2688-4056-b65c-5841a30b9e7d",
                "in_reuse": true,
                "latest_activity": "5d207fc1-761e-4c1b-baf3-75e6ffbf7f1f",
                "latest_activity_date": "2020-10-01T07:11:34.111Z",
                "latest_activity_location": {
                    "name": "retail 1"
                }
            }
        ],
        "passport_history": [
            {
                "asset": "9a29c6a6-10ad-4c25-a5bf-1dfac59aa675",
                "activity": "ecfcfa57-89fd-48ee-aaa8-6b74ddcd59cb",
                "date": "2020-11-01T19:11:34.111Z",
                "location": {
                    "name": "warehouse 1"
                }
            },
            {
                "asset": "9a29c6a6-10ad-4c25-a5bf-1dfac59aa675",
                "activity": "d922c237-7041-4c01-8272-161941698900",
                "date": "2020-10-01T19:11:34.111Z"
            },
            {
                "asset": "9a29c6a6-10ad-4c25-a5bf-1dfac59aa675",
                "activity": "5d207fc1-761e-4c1b-baf3-75e6ffbf7f1f",
                "date": "2020-09-01T19:11:34.111Z"
            },
            {
                "asset": "9a29c6a6-10ad-4c25-a5bf-1dfac59aa675",
                "activity": "1028b545-b5f5-4e3c-9dbc-64561ce91f1b",
                "date": "2020-09-01T19:11:34.111Z"
            },
            {
                "asset": "9a29c6a6-10ad-4c25-a5bf-1dfac59aa675",
                "activity": "5d207fc1-761e-4c1b-baf3-75e6ffbf7f1f",
                "date": "2020-10-01T07:11:34.111Z",
                "location": {
                    "name": "retail 1"
                }
            }
        ]
    }
    ```