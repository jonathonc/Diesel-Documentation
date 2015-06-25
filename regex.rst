Regex
=====

Regex.Match
-----------
Searches an input string for all occurrences of a regular expression and returns the value of the (matchIndex)th match.

Overloads
~~~~~~~~~
1. **Regex.Match(String inputString, String regexPattern, Int matchIndex): String**

Sample::

  record -> 'Name' : Regex.Match(record['Name'] to String, "([A-Z][a-zA-Z]*\s*)+", 1)

Regex.Word
-----------
A property (not a method) that stores a regular expression equivalent to the 'get word' expression. Used in conjunction with Regex.Match like so::

  record -> 'Name' : Regex.Match(record['Name'] to String, Regex.Word, 1);