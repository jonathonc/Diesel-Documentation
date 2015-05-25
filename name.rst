Name
====

Name.CreateFormal
-----------------

It will attempt to create the following "Mr Smith"
- If the title isn't equal to Mr, Mrs, Dr, Ms or Miss it will return null
- If the title is less than two characters it will return null

It be default proper cases everything

**Name.CreateFormal(string title, string surname) : String**

Name.TryCreate
--------------

Attempts to find a valid name based on the defined character limit. Automatically
proper cases all output.

**Name.TryCreate(int characterLimit, string defaultText, params string[] name) : string**

Sample::

  String name  = Name.TryCreate(15, "Sir/Madam", title, record['FirstName'] to String);

