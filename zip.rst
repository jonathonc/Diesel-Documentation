Zip
===

Properties
----------

Settings
~~~~~~~~
The zip file settings, including password and compression level.

Settings.Password
^^^^^^^^^^^^^^^^^^
- **Stores type:** String
- **Effect:** Sets the zip file password. If left unset, default is no password.

Sample::

  File[] filesForZip = Collection.Create(csvFile).Map(x -> x to File);
  ZipFile zipFile = Zip.CreateFile("CSV File.csv #{now}.zip", filesForZip);
  zipFile.Settings.Password = 'MagicCarpet1';

Settings.CompressionLevel
^^^^^^^^^^^^^^^^^^^^^^^^^
- **Stores type:** Int
- **Effect:** Sets the compression level of the zip file. A higher value means greater compression.

Settings.CompressionMethod
^^^^^^^^^^^^^^^^^^^^^^^^^^
- **Stores type:** String
- **Effect:** Sets the compression method of the zip file.

**Possible values:**

- "None"
- "BZip2"
- "Deflate"

Settings.EncryptionAlgorithm
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
- **Stores type:** String
- **Effect:** Sets the encryption algorithm of the zip file.

**Possible values:**

- "None"
- "PkzipWeak"
- "WinZipAes128"
- "WinZipAes256"

Zip.CreateFile
---------------
Creates a zip file from a collection of files.

Overloads
~~~~~~~~~
1. **ZipFile.Create(String fileName, File[] filesForZip): ZipFile**

Sample::

  File[] filesForZip = Collection.Create(csvFile).Map(x -> x to File);
  ZipFile zipFile = Zip.CreateFile("Name.zip", filesForZip);