# Code lists

# Summary

Some fields refer to codelists, to limit and standardise the possible values of the fields, in order to promote data interoperability.

Codelists can either be open or closed. Closed codelists are intended to be comprehensive. Open codelists are intended to be representative, but not comprehensive.

Publishers must use the codes in the codelists, unless no code is appropriate. 

If no code is appropriate and the codelist is open, then a publisher may use a new code outside those in the codelist. If no code is appropriate and the codelist is closed, an update to the standard may be requested.

> When using a new code in an Open codelist, Publishers are encouraged to also publish their codelist<sup>1</sup>. 

# Lists

### Activity Types
(Closed)

Used to facilitate comparison between cycles and to identify the "starting" activity which is used to count the number of times each individual asset moves through the cycle.

[activity_types.csv](activity_types.csv)

### Allergens
(Closed)

Used to identfy allergens contained or in contact with the asset. Currently this includes the 14 (ingested) allergens which are legally required by UK law.

[allergens.csv](allergens.csv)

### Cleaning Methods
(Open)

Used to identify type of cleaning needed for each asset type.

[cleaning_methods.csv](cleaning_methods.csv)

### Materials
(Open)

Used to identify type of material in each asset type. Note: this list is intended for broad categorisation, for detailed analysis publishers will need to provide their own code list.

[materials.csv](materials.csv)

### Packaging Types
(Open)

Used to identify type of packaging.

[packaging_types.csv](packaging_types.csv)

### Reuse Models
(Closed)

Used to identify the reuse model of a cycle, i.e. the refill model.

[reuse_models.csv](reuse_models.csv)


### Tracker Types
(Open)

The type of tracking that is used on each individual reusable asset in order to match it with the electronic digital passport.

[tracker_types.csv](tracker_types.csv)

---

<sup>1</sup> A future version of this standard could [support custom extensions](https://standard.open-contracting.org/latest/en/guidance/map/extensions/) to promote data interoperability with Open codelists.
