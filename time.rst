Time
====

Note: A DateTime object can be of type GlobalTime or LocalTime.

Time.Add
--------
Returns a new DateTime that is the value of the input dateTime plus (number * timePeriod)

Overloads
~~~~~~~~~
1. **Time.Add(DateTime dateTime, BaseTimePeriod timePeriod, Int number): DateTime**

- timePeriod cannot be null
- If number is negative, subtracts instead of adding

Sample::

  LocalTime time = Time.CurrentLocal();
  LocalTime sixDaysLater = Time.Add(time, Time.Day, 6);

Time.Component
--------------
Retrieves a component of the specified temporal value. A component is a read-only collection. The component will contain the fields of millisecond, second, minute, hour, day, dayOfWeek, dayOfYear, month, and year.

Overloads
~~~~~~~~~
1. **Time.Component(DateTime time): Collection**

Sample::

  LocalTime time = Time.CurrentLocal();
  Collection component = Time.Component(time);

Time.CurrentLocal
-----------------
Returns a LocalTime object corresponding to the current time at which this method is called.

Overloads
~~~~~~~~~
1. **Time.CurrentLocal(): LocalTime**

Sample::

  LocalTime now = Time.CurrentLocal();

Time.GetDayOfWeek
-----------------
Returns the day of the week of the specified temporal value.

Overloads
~~~~~~~~~
1. **Time.GetDayOfWeek(DateTime time): Int**

- The returned integer ranges from 0 for Sunday to 6 for Saturday

Sample::

  LocalTime time = Time.CurrentLocal();
  Int32 dayOfWeek = Time.GetDayOfWeek(time);

Time.GetEndOf
-------------
Calculates the point in time that is the end of the specified period for the specified date and time.

Overloads
~~~~~~~~~
1. **Time.GetEndOf(DateTime dateTime, BaseTimePeriod timePeriod): DateTime**

- timePeriod cannot be null

Sample::

  LocalTime endOfToday = Time.GetEndOf(Time.CurrentLocal(), Time.GetTimePeriod("Day"))

Time.GetIntervals
-----------------
Returns the number of specified timePeriods between time1 and time2. If time1 is earlier than time2, the return value will be negative.

Overloads
~~~~~~~~~
1. **Time.GetIntervals(DateTime time1, DateTime time2, BaseTimePeriod timePeriod): Int**

Sample::

  Int32 value = Time.GetIntervals(Time.CurrentLocal(), Convert.ToLocalTime(record['DeliveryDate']), 
    Time.GetTimePeriod("Month"))


Time.GetStartOf
---------------
Calculates the point in time that is the start of the specified period for the specified date and time.

Overloads
~~~~~~~~~
1. **Time.GetStartOf(DateTime dateTime, BaseTimePeriod timePeriod): DateTime**

Sample::

  LocalTime beginningOfThisMonth = Time.GetStartOf(Time.CurrentLocal(), Time.GetTimePeriod("Month"));

Time.GetTimePeriod
------------------
Returns the BaseTimePeriod specified by the timeString.

Overloads
~~~~~~~~~
1. **Time.GetTimePeriod(String timeString): BaseTimePeriod**

Valid timeStrings include:
 
- "Day" 
- "Month"   
- "Year"  

Sample::

  record -> 'FirstRegoDateMonthInterval' : Time.GetIntervals(Time.CurrentLocal(), Convert.ToLocalTime(record['DeliveryDate']), Time.GetTimePeriod("Month"))

Time.IsFuture
-------------
Returns true if the specified time is in the future, false otherwise.

Overloads
~~~~~~~~~
1. **Time.IsFuture(DateTime time): Bool**
2. **Time.IsFuture(Object time): Bool**

- If using overload 2, the time Object will be cast to a DateTime before comparison

Sample::

  Record[] smsRecords = records.Where(record -> record.Mobile != null && record.Email == null && Time.IsFuture(record.ApptDate to LocalTime));

Time.IsPast
-----------
Returns true if the specified time is in the past, false otherwise.

Overloads
~~~~~~~~~
1. **Time.IsPast(DateTime time): Bool**
2. **Time.IsPast(Object time): Bool**

- If using overload 2, the time Object will be cast to a DateTime before comparison

Sample::

  Record[] emailRecords = records.Where(record -> record.Email != null && Time.IsPast(record.ApptDate to LocalTime));

Time.Subtract
-------------
Returns the DateTime which is the point in time a specified number of periods before the specified dateTime.

Overloads
~~~~~~~~~
1. **Time.Subtract(DateTime dateTime, BaseTimePeriod timePeriod, Int number): DateTime**

- timePeriod cannot be null
- If number is negative, adds instead of subtracts

Sample::

  LocalTime sixDaysAgo = Time.Subtract(Time.CurrentLocal(), Time.GetTimePeriod("Day"), 6);
