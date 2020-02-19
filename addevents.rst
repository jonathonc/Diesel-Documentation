Add Events
==========

AddEvent.CreateLink
-------------------
A function to create the "Click to Add Calendar" new feature. This function has a lot of parameters, some are optional. 
You can have a look at them here: https://www.addevent.com/documentation/direct-url-method

Overloads
~~~~~~~~~
1. **String link = AddEvent.CreateLink(String clientId, String title, String startDate, Int duration, String location, String description, String service, String calname) : UriAddress**

Sample::

    String link = AddEvent.CreateLink('client', 'Does 1 + 10 / 2 = 1000 & more maths...?', '2019-07-19 13:00', 60, 'Australia/Sydney', 'Does 1 + 10 / 2 = 1000 & more maths...?', 'Does 1 + 10 / 2 = 1000 & more maths...?', 'outlook', 'use-title');
