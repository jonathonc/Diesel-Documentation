EmailAddress
============

EmailAddress.CanParse
---------------------
Returns true if the input string can be parsed as an email address, false otherwise.

Overloads
~~~~~~~~~
1. **EmailAddress.CanParse(String str): Bool**

- parser defaults to the phone number parser defined in the language settings.
- str cannot be null

Sample::

  EmailAddress.CanParse("blargh") == false;
  EmailAddress.CanParse("an_actual_email@gmail.com") == true;

EmailAddress.Parse
------------------
Converts a String to an EmailAddress.

Overloads
~~~~~~~~~
1. **EmailAddress.Parse(String str)**

- parser defaults to the phone number parser defined in the language settings.

Sample::

  EmailAddress email = EmailAddress.Parse("support@irwinsolutions.com");

EmailAddress.TryParse
---------------------
Tries to convert a String to an EmailAddress. Returns the resulting EmailAddress if it can convert, otherwise returns null.

Overloads
~~~~~~~~~~
1. **EmailAddress.TryParse(params String[] values)**

Sample::

  EmailAddresss email = EmailAddress.TryParse(email1, email2);
