PDF
===

Pdf.Create
----------
Creates a PDF file.

Overloads
~~~~~~~~~
1. **Pdf.Create(String fileName, String content): PdfFile**

- content is a HTML string

Sample::

  String pdfHtml = "<html><body><p>Words go here.</p></body></html>"
  PdfFile pdf = Pdf.Create("Name.pdf", pdfHtml);

Pdf.CreateFromWeb
-----------------
Creates a PDF file from a URI address.

Overloads
~~~~~~~~~
1. **Pdf.CreateFromWeb(String fileName, UriAddress uri): PdfFile**

Sample::

  UriAddress uri = UriAddress.Parse("https://www.google.com");
  PdfFile pdf = Pdf.CreateFromWeb("Name.pdf", uri);