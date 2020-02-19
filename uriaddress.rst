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
Url encodes text for use within mail to query strings, returns an encoded mailto UriAddress.

Overloads
~~~~~~~~~
1. **UriAddress.EncodeMailToPart(String str): String

Sample:: 

  UriAddress.EncodeMailToPart('Does 1 + 10 / 2 = 1000 & more maths...?');
  // Output: 'Does%201%20%2B%2010%20%2F%202%20%3D%201000%20%26%20more%20maths...%3F'

UriAddress.EncodeQueryStringPart
--------------------------------
Url encodes text for use within query strings

Overloads
~~~~~~~~~
1. UriAddress.EncodeQueryStringPart(String str) : String

Sample::

  String urlPart = UriAddress.EncodeQueryStringPart('Does 1 + 10 / 2 = 1000 & more maths...?');
  // Output: 'Does+1+%2b+10+%2f+2+%3d+1000+%26+more+maths...%3f'
