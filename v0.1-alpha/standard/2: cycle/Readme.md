# Cycle

Defines the steps a piece of packaging progresses through in each reuse cycle.

## Summary

Reuse cycles are unique depending on the asset and the reuse model amoungst other variables. Any reuse.id dataset should be fully self describing, including the reuse cycle itself.

The cycle is made up of "Activities" which mark the movment of the reusable asset through each step in the cycle. 

- [ ] **TODO**: diagram of example cycle here

Each Activity can have one or more preceeding Activities, that define how the reusable asset moves through the cycle. An Activity with no preccedding Activity is the point(s) at which this asset enters this reuse cycle. An Activity that is referenced by zero other Activities in this cycle is the point(s) where the asset leaves this cycle.

- [ ] **TODO**: diagram here showing examples of entry Activities (eg "Asset Purchase"), and exit Activities (eg: "Sent to Recycling")

Activity Types are used to facilitate comparison between cycles and further business specific data which is outside the scope of this standard.

## Fields

### Cycle

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
|cycle_id|UUID|Yes|Unique identifier|
|name|string|No|Descriptive name|
|activities|Array|Yes|Array of Activity objects, describing each step in the cycle|

### Activities

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
|activity_id|UUID|Yes|Unique identifier|
|activity_type|List|Yes|Single value from "Activity Type" codelist|
|name|string|Yes|Descriptive name|
|previous_activities|Array|No|Array of UUIDs referring to the zero, one ore more activities within this cycle that directly preceeds this one. |
