---
title: Technical definitions
description: a list of terms and definitions used within the Reuse Standard.
---

# Technical Definitions

## Options

 The standard is intended to be flexible enough to cover one or more of the following data sets:

 - Definition of specific reuse cycles
 - Description of the types of reusable assets (including physical properties)
 - Description of the "state" of individual reusable assets (e.g. packaging) at any point in time
 - Describing the detailed "history" of individual reusable assets across any time period

## Data for individual reusable items: Digital Passports

A Digital Passport is the digital vehicle for storing data that has been captured in a standardised way, i.e. via a data standard. Think of it like your own passport collecting location information about you as you travel, but instead of representing a person, a Digital Passport represents an individual piece of packaging and its journey.

This Standard includes two optional ways to represent Digital Passports. Users of the Standard may choose to include one or both of these, or to exclude the Passport completely (only including reuse cycles and maybe asset types).

1. Passport: this represents the "state" of the individual reusable item at a specific point in time. Think of this like using the Passport to identify in which country a person is currently locationed and how many times they have been though a different country. Although, rather than country, the Digital Passport summary for a reusable item will include information like how many times it has been reused and at what stage in the reuse cycle is it now.

1. Passport History: This is the detailed history of every step in the reuse cycle that each individual reusable asset has been through.

## Validation

This standard utilises the *JSON Schema Draft 7* mechanism to validate records being exchanged. *JSON Schema* is an IETF proposed standard for validating the formatting of a received JSON data.

JSON is the de facto standard for exchanging data over the web.

JSON Schema allows the structure of JSON documents to be described and documented and allows data to be validated against the schema. 

## Field Types

When referenced in the standard, field types refer to the following data types.

Field Type | Description
---------- | -----------
String|Alphanumeric data, appropriately escaped and encoded for inclusion in a JSON document. 
Number|Numeric value, with either zero or two decimal points (eg: 12.20 or 7.00). 
List|Alphanumeric string data, limited to specific acceptable values. The acceptable values are defined in the relevant internal [code list](./../4_Code_Lists/4_1_Code_Lists.md) or in external standards or recognised code lists.
UUID|A globally unique identification string using "RFC 4122" (https://www.ietf.org/rfc/rfc4122.txt, see also http://guid.one/).
Numeric|A numeric value, either as an integer or a  floating point number.
DateTime|An RFC 3339 compliant date string, including date, time, and time zone.
URL|A String, representing a valid URL including protocol, host, and if applicable, a path and query string.
Boolean|A boolean string of either true, or false.
Object|A valid JSON object, representing a collection of additional values that are grouped together.
Array|A valid JSON array, representing a collection of objects.

## Custom Field Types

A few more complex field types are defined as well.

### Date Range

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
start|DateTime|Yes|When the date range starts
end|DateTime|Yes|When the date range ends

### Money

Field Name | Data Type | Required | Description
---------- | --------- | -------- | -----------
currency|List|Yes|Alphabetic Currency code from [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html)|
amount|Number|Yes|Value amount|
