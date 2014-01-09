Object: Culture
===============

This object contains methods for retrieving cultures.

Get(String)
-----------

Returns the culture associated with the specified code.

::

  Culture : Culture.Get(String code)

*Notes*

- Null references are not permitted.
- The following cultures are supported

  - 'en-AU' (English - Australia)
  - 'en-US' (English - United States)

*Sample Code*

::

  Object culture = Culture.Get('en-AU');