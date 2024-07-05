---
title: Org
description: The organisation responsible for the reuse lifecycle and reusable assets
---

# Org

The organisation responsible for the reuse lifecycle and reusable assets

## Fields

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
name|String|Yes|Name of the organisation|
org_id|Standard|Yes|Unique identifier for organisation using [Org.Id format](https://github.com/OpenDataServices/org-ids/). Where possible, using company numbers as the baseline for unambiguous identification. This allows an internationally unique ID (EG: An identifier of the form GB-COH-XXXXXXXX for a UK-registered company). To lookup the format for a location & organisation type use [org-id.guide](http://org-id.guide/)|
postcode|String|No|Postcode for organisation headquarters|

## Diagram

``` mermaid
erDiagram
  ORG {
    name String
    org_id Standard
    postcode String
  }
  ORG ||--o{ ORDER : places
    ORDER ||--|{ LINE-ITEM : contains
    ORG }|..|{ DELIVERY-ADDRESS : uses
```

[Schema](./../schema/org.schema.json)