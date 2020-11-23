# reuse.id : Technical Definition

## Why a reuse Open Data Standard?

The opportunity for an Open Data Standard to accelerate and de-risk the shift towards reusable products (especially packaging) is significant. 

- [ ] **TODO**: link to white paper and/or web page with detailed background

## Summary

The goal of this Open Data Standard, is to identify and standardise definitions that will support the launch, scaling, analysis and regulation of safe, optimised and compliant reuse systems. 

This is acheived by:

- Creating a shared Vocabulary: Common definitions ensure everyone understands what words mean in the context of the data being collected (in this case, reuse).

- Facilitating Data transfer & sharing: enabling organisations (including reuse business, environmental regulators and researchers) to share *only* the data that is relevant, while enabling the wider goal of improving and growing reuse business models.

## Notes

 - [ ] **TODO**: extend notes on use cases

 The standard is intended to be flexible enough to use in any of the follow scenarios:

 - Defining and sharing specific reuse cycles
 - Describing and sharing the "state" of individual resuable assets (eg packaging) at any point in time
 - Describing and sharing the detailed "history" of individual resuable assets across any time period

 ## Data for individual reusable items: Digital Passports

A Digital Passport is the digital vehicle for storing data that has been captured in a standardised way, i.e. via a data standard. Think of it like your own passport collecting information location about you as you travel, but instead of representing a person, a Digital Passport represents an individual piece of packaging and its journey.

This Standard includes two optional ways to represent Digital Passports. Users of the Standard may choose to include one or both of these, or to exclude the Passport completely (using the Standard to share reuse cycles and maybe Asset Types only).

1. Passport Summary: this represents the "state" of the individual reusable item at a specific point in time. Think of this like using the Passport to idenify in which country a person is currently locationed and how many times they have been though a different country. Although, rather than country, the Digital Passport summary for a reusable item will include information like how many times it has been reused, at what stage in the reuse cycle is it now and which (if any) batch of consumable product it currently contains.

1. Passport History: This is the detailed history of every step in the reuse cycle that each individual reusable asset has been through.

## Validation

This standard utilizes the *JSON Schema Draft 7* mechanism to validate records being exchanged. *JSON Schema* is an IETF proposed standard for validating the formatting of a received JSON data.

JSON is the de facto standard for exchanging data over the web.

JSON Schema allows the structure of JSON documents to be described and documented and allows data to be validated against the schema. 

## Reference Information

### Field Types

When referenced in the standard, field types refer to the following data types.

<table>
  <tr>
    <td>Field Type</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>String</td>
    <td>Alphanumeric data, appropriately escaped and encoded for inclusion in a JSON document. </td>
  </tr>
  <tr>
    <td>List</td>
    <td>Alphanumeric string data, limited to specific acceptable values. The acceptable values are defined in relevant code list.</td>
  </tr>
  <tr>
    <td>UUID</td>
    <td>A globally unique identification string using "RFC 4122" (https://www.ietf.org/rfc/rfc4122.txt, see also http://guid.one/).</td>
  </tr>
  <tr>
    <td>Numeric</td>
    <td>A numeric value, either as an integer or a  floating point number.</td>
  </tr>
  <tr>
    <td>Date</td>
    <td>An RFC 3339 compliant date string, including date, time, and time zone.</td>
  </tr>
  <tr>
    <td>URL</td>
    <td>A String, representing a valid URL including protocol, host, and if applicable, a path and query string.</td>
  </tr>
  <tr>
    <td>Boolean</td>
    <td>A boolean string of either true, or false.</td>
  </tr>
  <tr>
    <td>Object</td>
    <td>A valid JSON object, representing a collection of additional values that are grouped together.</td>
  </tr>
  <tr>
    <td>Array</td>
    <td>A valid JSON array, representing a collection of objects.</td>
  </tr>
</table>

- [ ] **TODO**: data types for internal reference (eg asset type ID), external standards format (eg country code or product type), etc

## Fields

|Field Name|Data Type|Required|Description|
|:-|:-|:-|:-|
|org|Object|Yes|The single organisation responsible for this resue dataset|
|date|Date|Yes|When this data was compiled|
|date_range_start|date|No|Optional date from which the Passport data starts. *Required* if and passport_history is present|
|date_range_end|date|No|Optional date on which the Passport data ends|
|cycles|Array|Yes|Defines the reuse cycle(s)|
|asset_types|Array|No|Describes the types of physical reusable assets (eg packaging) that are moving through the reuse cycles *Required* if and Passport fields are present|
|passport_summary|Array|No|Describes the current state of all individual reusuable asset as at date_range_end (or date)|
|passport_history|Array|No|Record of all Activities that each individual reusuable asset has been through between date_range_start and date_range_end|


