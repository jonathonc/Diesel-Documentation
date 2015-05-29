PhoneNumber
===========

PhoneNumber.Parse()
--------------------
Converts a phone number represented as a String to a PhoneNumber object.

Overloads
~~~~~~~~~
1. **PhoneNumber.Parse(String phoneNumber): PhoneNumber**

Sample::

  PhoneNumber phNo = PhoneNumber.Parse("0411202518");

PhoneNumber.TryParse()
-----------------------
Tries to convert strings into a mobile phone number. Tries to convert argument 1, then argument 2, then argument 3 etc. until one of them can be converted. Returns the first argument it can convert to a phone number as a phone number.

Overloads
~~~~~~~~~
1. **PhoneNumber.TryParse(params String[] potentialPhoneNumbers): PhoneNumber**

Sample::

  record -> 'Mobile' : PhoneNumber.TryParse(record['Mobile'] to String, record['HomePhone'] to String, record['BusinessPhone'] to String)