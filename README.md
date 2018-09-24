# Object Diagram (M0) to JSON

This VTL report converts a set MagicDraw Object Instances into an equivalent set of JSON representations.

## Method of Transformation

All data in an class instance is stored in one or more `slots`. `Slots` store things such as attributes, and associations.

Each slot is converted to a property of the same name.

To maintain compatibility with NIST 1500 generated JSON Schemas, each Object contains the property `@type` containing the value in the form of `{Package}.{ClassName}`.

Each Object instance will result in a separate JSON property the same as the object, and whose value is the object and its dereferenced associations.

## Associations

All references (e.g. directed associations) are dereferenced to form a single JSON instance.

## Handling of Multiplicities

Attributes or associations at M1 having a multiplicity with a upper cardinality of greater than 1 are generated as arrays.