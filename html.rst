HTML
====

Html.MailTo
------------
A function to create the email mailto link, includes encoding to handle things like "&"

Overloads 
~~~~~~~~~
1. **Html.MailTo(String email, String subject, String body)**

Sample:: 

    String email = 'jonathonc@irwinsolutions.com'
    String subject = 'Does 1 + 10 / 2 = 1000 & more maths...?'
    String body = 'Hello\nThis is a new line\nDoes 1 + 10 / 2 = 1000 & more maths...?'
    