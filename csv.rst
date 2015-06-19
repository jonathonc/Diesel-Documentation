CSV
===

Comma-separated values file

Csv.CreateWithDefaults
----------------------
Creates a string representing the contents of a CSV file from a field accessor (e.g. a Record[] array of Record objects) and some lambda expressions using the fields of the accessor object. Often used in conjunction with String.CreateFile to create a CSV file.

Overloads
~~~~~~~~~
1. **Csv.CreateWithDefaults(IEnumerable<IObjectFieldAccessor> accessor, params LambdaArgument[]): String**

Sample::

  TextFile csvFile = String.CreateFile("NoContact.csv", Csv.CreateWithDefaults(noContactRecords,
    record -> 'CustNo' : record.CustNo,
    record -> 'FirstName': record.FirstName
  ));