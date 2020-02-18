Add Events
==========

AddEvent.CreateLink
-------------------
A function to create the "Click to Add Calendar" new feature. This function has a lot of parameters, some are optional. 
You can have a look at them here: https://www.addevent.com/documentation/direct-url-method

Overloads
~~~~~~~~~
1. String link = AddEvent.CreateLink(String client, String startDate, Int duration, String title, String description, String location, String service, String calname);

Sample::

    String link = AddEvent.CreateLink('client', '2019-07-19 13:00', 60, 'This is an event title', 'Does 1 + 10 / 2 = 1000 & more maths...?', 'Australia/Sydney', 'outlook', 'use-title');
