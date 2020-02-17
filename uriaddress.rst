UriAddress
==========

A URI address is a uniform resource identifier. A URL is a type of URI.

UriAddress.CanParse
-------------------
Returns whether a string can be parsed as a URI address.

Overloads
~~~~~~~~~
1. **UriAddress.CanParse(String str): Bool**

- str cannot be null

Sample::

  String str1 = "https://www.google.com";
  String str2 = "buuutttttttsss";
  UriAddress.CanParse(str1) == true;
  UriAddress.CanParse(str2) == false;

UriAddress.Parse
----------------
Parses a string as a URI address. Returns the resulting URI address.

Overloads
~~~~~~~~~
1. **UriAddress.Parse(String str): UriAddress**

- str cannot be null

Sample::

  UriAddress google = UriAddress.Parse("https://www.google.com");

UriAddress.TryParse
-------------------
Attempts to parse a string as a URI address. If it can be parsed, returns the resulting URI address. If it cannot be parsed, returns null.

Overloads
~~~~~~~~~
1. **UriAddress.TryParse(): UriAddress**

Sample::

  UriAddress.TryParse("buuutttttttsss") == null;
  UriAddress google = UriAddress.TryParse("https://www.google.com");


UriAddress.EncodeMailToPart
---------------------------
Url encodes text for use within mail to query strings

Overloads
~~~~~~~~~
1. UriAddress.EncodeMailToPart(String str)

Sample:: 

  UriAddress.EncodeMailToPart('Does 1 + 10 / 2 = 1000 & more maths...?');


UriAddress.EncodeQueryStringPart
--------------------------------
Url encodes text for use within query strings

Overloads
~~~~~~~~~
String urlPart = UriAddress.EncodeQueryStringPart('Does 1 + 10 / 2 = 1000 & more maths...?');
