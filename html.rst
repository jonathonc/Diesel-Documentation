HTML
====

Html.MailTo
------------
A function to create the email mailto link, includes encoding to handle things like "&" 

Overloads 
~~~~~~~~~
1. **Html.MailTo(String email, String subject, String body) : String**

Sample:: 

    String email = 'jonathonc@irwinsolutions.com';
    String subject = 'Does 1 + 10 / 2 = 1000 & more maths...?';
    String body = 'Hello\nThis is a new line\nDoes 1 + 10 / 2 = 1000 & more maths...?';

    String mailTo = Html.MailTo(email, subject, body);  
    // mailTo = "mailto:jonathonc@irwinsolutions.com?subject=Does%201%20%2B%2010%20%2F%202%20%3D%201000%20%26%20more%20maths...%3F&body=Hello%0AThis%20is%20a%20new%20line%0ADoes%201%20%2B%2010%20%2F%202%20%3D%201000%20%26%20more%20maths...%3F"
