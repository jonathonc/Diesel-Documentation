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
**String.IndexOf(String inputString, String searchString, Bool ignoreCase, ICultureAccessor cultureAccessor): Int**
**String.IndexOf(String inputString, String searchString, Bool ignoreCase): Int**
**String.IndexOf(String inputString, String searchString): Int**

- cultureAccessor defaults to the culture defined in settings
- ignoreCase defaults to false


Sample::

  String word = "apples";
  Int32 whereIsL = String.IndexOf(word, "l");