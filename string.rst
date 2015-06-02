String
======

String.Contains
---------------
Finds a substring inside an input string.

Overloads
~~~~~~~~~
1. **String.Contains(String inputString, String searchString, Bool ignoreCase, ICultureAccessor cultureAccessor): Bool**
2. **String.Contains(String inputString, String searchString, Bool ignoreCase): Bool**
3. **String.Contains(String inputString, String searchString): Bool**

- cultureAccessor defaults to the culture defined in settings
- ignoreCase defaults to false

Sample::

  String word = "bed";
  Bool containsCapitalE = String.Contains(word, "E");
  Bool containsE = String.Contains(word, "e", false);

String.CreateFile
---------------
Creates a file with fileName containing content.

Overloads
~~~~~~~~~
1. **String.CreateFile(String fileName, String content): File**

Sample::

  TextFile file = String.CreateFile("file.txt", "These are file contents");


String.EndsWith
---------------

Overloads
~~~~~~~~~
1. **String.EndsWith(String inputString, String searchString, Bool ignoreCase, ICultureAccessor cultureAccessor): Bool**
2. **String.EndsWith(String inputString, String searchString, Bool ignoreCase): Bool**

- cultureAccessor defaults to the culture defined in settings
- ignoreCase defaults to false

Sample::

  String word = "apples";
  Bool endsWithS = String.EndsWith(word, "s")


String.IndexOf
---------------
Finds the zero-based starting index in the input string of the given substring searchString, provided the substring is part of the input string. If searchString is String.Empty, returns 0. If searchString is not in inputString, returns -1.

Overloads
~~~~~~~~~
1. **String.IndexOf(String inputString, String searchString, Bool ignoreCase, ICultureAccessor cultureAccessor): Int**
2. **String.IndexOf(String inputString, String searchString, Bool ignoreCase): Int**
3. **String.IndexOf(String inputString, String searchString): Int**

- cultureAccessor defaults to the culture defined in settings
- ignoreCase defaults to false


Sample::

  String word = "apples";
  Int32 whereIsL = String.IndexOf(word, "l");

String.Length
-------------
Returns the length of a string as an integer.

Overloads
~~~~~~~~~
1. **String.Length(String str): Int**

Sample::

  String.Length("word") == 4;

String.ToProper
---------------
Converts a string to proper casing, i.e. converts first letter of each word to uppercase.

Overloads
~~~~~~~~~
1. **String.ToProper(String str, ICultureAccessor cultureAccessor): String**
2. **String.ToProper(String str): String**

- cultureAccessor defaults to the culture defined in settings
- throws an exception if str is null

Sample::

  String.ToProper("mrs anderson") == "Mrs Anderson";

String.ToLower
--------------
Converts a STRING to all lowercase.

Overloads
~~~~~~~~~
1. **String.ToLower(String str, ICultureAccessor cultureAccessor): String**
2. **String.ToLower(String str): String**

- cultureAccessor defaults to the culture defined in settings
- throws an exception if str is null

Sample::
  String.ToLower("WORD") == "word";

String.ToUpper
--------------
Converts a string to ALL UPPERCASE.

Overloads
~~~~~~~~~
1. **String.ToUpper(String str, ICultureAccessor cultureAccessor): String**
2. **String.ToUpper(String str): String**

- cultureAccessor defaults to the culture defined in settings
- throws an exception if str is null

Sample::

  String.ToUpper("word") == "WORD";

String.Trim
-----------
Removes all leading and trailing whitespace characters from a string.

Overloads
~~~~~~~~~~
1. **String.Trim(String str): String**

Sample::

  String.Trim("       space        ") == "space";