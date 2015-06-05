EmailAddress
============

EmailAddress.Parse
------------------
Converts a String to an EmailAddress.

Overloads
~~~~~~~~~
1. **EmailAddress.Parse(String str, IPhoneNumberParser parser)**
2. **EmailAddress.Parse(String str)**

- parser defaults to the phone number parser defined in the language settings.

Sample::

  emailMessage.From = EmailAddress.Parse("support@irwinsolutions.com");

EmailAddress.TryParse
---------------------
Tries to convert a String to an EmailAddress. Returns the resulting EmailAddress if it can convert, otherwise returns null.

Overloads
~~~~~~~~~~
1. **EmailAddress.TryParse(params String[] values)**

Sample::
  record -> 'Email': EmailAddress.TryParse(record['Email'])