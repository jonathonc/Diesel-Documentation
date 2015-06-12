Zip
===

Zip.CreateFile
---------------
Creates a zip file from a collection of files.

Overloads
~~~~~~~~~
1. **ZipFile.Create(String fileName, File[] filesForZip): ZipFile**

Sample::

  File[] filesForZip = Collection.Create(csvFile).Map(x -> x to File);
  ZipFile zipFile = Zip.CreateFile("Name.zip", filesForZip);