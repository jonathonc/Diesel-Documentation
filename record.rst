Record
======

Record.Contains
---------------
Returns whether a field with the specified name exists in the specified Record object.

Overloads
~~~~~~~~~
1. **Record.Contains(Record accessor, String field): Bool**

- accessor cannot be null
- field cannot be null

Record.CreateMutable
--------------------
Creates a mutable record.

Overloads
~~~~~~~~~
1. **Record.CreateMutable(IEnumerable<KeyValuePair<String, Object>> selectors): Record**

- selectors cannot be null
- none of the keys in selectors can be null
- none of the keys in selectors can be duplicates