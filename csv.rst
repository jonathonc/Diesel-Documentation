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

  String csv = Csv.CreateWithDefaults(records,
    record -> 'Mobile' : record.Mobile,
    record -> 'FirstName': record.FirstName
  );
  
Creating a CSV file::

  TextFile csvFile = String.CreateFile("data.csv", Csv.CreateWithDefaults(records,
    record -> 'CustNo' : record.CustNo,
    record -> 'FirstName': record.FirstName
  ));
