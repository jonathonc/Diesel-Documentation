TimeFormats
===========

Used in conjunction with Convert.ToString() to format a time to a String.

::

  Convert.ToString(Time.CurrentLocal(), TimeFormats.LongYear); // 2015

TimeFormats.DayOfMonth
--------------------------------
- **Format string:** "dd" 
- **Meaning:** The two-digit number representing the day of the month   

**Example:**
::
  Convert.ToString(Time.CurrentLocal(), TimeFormats.DayOfMonth) == 19;

TimeFormats.GeneralDateShortTime
--------------------------------
- **Format string:** "g"  
- **Meaning:** A combination of short date and short time patterns, separated by a space. 

**Example:** 
::
  Convert.ToString(Time.CurrentLocal(), TimeFormats.GeneralDateShortTime) == "19/06/2015 2:48 PM";

TimeFormats.GeneralDateLongTime
--------------------------------
- **Format string:** "G"  
- **Meaning:** A combination of the short date and long time patterns, separated by a space.  

**Example:** 
::
  Convert.ToString(Time.CurrentLocal(), TimeFormats.GeneralDateLongTime)

TimeFormats.LongDate
--------------------------------
- **Format string:** "D"  
- **Meaning:** The day of the week, a comma, followed by the day of the month in "dd" format, the month written out in full, a comma, and the year in "yyyy" format.  

**Example:** 
::
  Convert.ToString(Time.CurrentLocal(), TimeFormats.LongDate) == "Friday, 19 June, 2015";

TimeFormats.LongDateShortTime
--------------------------------
- **Format string:** "f"
- **Meaning:** A combination of the long date and short time patterns, separated by a space.  
**Example:** Convert.ToString(Time.CurrentLocal(), TimeFormats.LongDateShortTime) == "Friday, 19 June, 2015 2:51 PM";

TimeFormats.LongDateLongTime
--------------------------------
- **Format string:** "F"  
- **Meaning:** Full date long time format specifier. Exact format depends on culture settings.

TimeFormats.LongDayOfWeek
--------------------------------
- **Format string:** "dddd"  
- **Meaning:** The day of the week written out as a full word.

**Example:** 
::
  Convert.ToString(Time.CurrentLocal(), TimeFormats.LongDayOfWeek) == "Friday";

TimeFormats.LongMonthName
--------------------------------
- **Format string:** "MMMM"  
- **Meaning:** The month written out as a full word.

**Example:** 
::
  Convert.ToString(Time.CurrentLocal(), TimeFormats.LongDate) == "June";

TimeFormats.LongTime
--------------------------------
- **Format string:** "T"  
- **Meaning:** Displays time in hours : minutes : seconds. Exact format depends on region settings, but en-US is "h:mm:ss"

**Example:** 
::
  Convert.ToString(Time.CurrentLocal(), TimeFormats.LongTime) == "3:40:00 PM";

TimeFormats.LongYear
--------------------------------
- **Format string:** "yyyy"  
- **Meaning:** The year written out in all four digits.

**Example:** 
::
  Convert.ToString(Time.CurrentLocal(), TimeFormats.LongDate) == "2015";

TimeFormats.Month
--------------------------------
- **Format string:** "MM"  
- **Meaning:** The month written out in 2-digit format.

**Example:** 
::
  Convert.ToString(Time.CurrentLocal(), TimeFormats.Month) == "06";

TimeFormats.RFC1123
--------------------------------
- **Format string:** "r" or "ddd, dd MMM yyyy HH':'mm':'ss GMT'"
- **Meaning:** The day of the week in three-letter format, a comma, the 2-digit day, the three-letter month, the four-digit year, the two-digit hour of the 24-hour clock, a colon, the 2-digit minute, a colon, the 2-digit second, the letters GMT. 

**Example:** 
::
  Convert.ToString(Time.CurrentLocal(), TimeFormats.RFC1123) == "Fri, 19 Jun 2015 15:47:00 GMT";

TimeFormats.ShortDate
--------------------------------
- **Format string:** "d"  
- **Meaning:** Short date pattern. Exact format depends on region settings, but for Australia it is equivalent to "d/MM/yyyy" format.

**Example:** 
::
  Convert.ToString(Time.CurrentLocal(), TimeFormats.ShortDate) == "19/06/2015";

TimeFormats.ShortDateShortTime
--------------------------------
- **Format string:** "G"  
- **Meaning:** Identical to GeneralDateLongTime

TimeFormats.ShortDayOfWeek
--------------------------------
- **Format string:** "ddd"  
- **Meaning:** The day of the week abbreviated to three letters. 

**Example:** 
::
  Convert.ToString(Time.CurrentLocal(), TimeFormats.ShortDayOfWeek) == "Fri";

TimeFormats.ShortMonthName
--------------------------------
- **Format string:** "MMM"  
- **Meaning:** The month abbreviated to three letters.

**Example:** 
::
  Convert.ToString(Time.CurrentLocal(), TimeFormats.ShortMonthName) == "Jun";

TimeFormats.ShortYear
--------------------------------
- **Format string:** "yy"  
- **Meaning:** The year abbreviated to the last two least significant digits.

**Example:** 
::
  Convert.ToString(Time.CurrentLocal(), TimeFormats.ShortDate) == "15";