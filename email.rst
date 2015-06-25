Email
=====

Properties
----------

Attachments
~~~~~~~~~~~
- **Stores type:** Collection of Files
- **Effect:** Adds attachments to the email message

Sample::

  EmailMessage internalEmailMessage = Email.CreateMessage();
  internalEmailMessage.Attachments = Collection.Create(csvFile).Map(x -> x to File);

Body
~~~~
- **Stores type:** String
- **Effect:** Sets email message body

Sample::

  EmailMessage emailMessage = Email.CreateMessage();
  emailMessage.Body = @"<!DOCTYPE html><html xmlns=http://www.w3.org/1999/xhtml><head><meta http-equiv=Content-Type content='text/html; charset=UTF-8'><title></title></head><body><p>Words go here.</p></body></html>";

From
~~~~
- **Stores type:** EmailAddress
- **Effect:** Sets email message to be from specified email address

Sample::

  EmailMessage emailMessage = Email.CreateMessage();
  emailMessage.From = EmailAddress.Parse("service@someDealership.com");

Recipients
~~~~~~~~~~
- **Stores type:** EmailRecipient or EmailRecipient[]
- **Effect:** Sets the recipients of this email message

Sample::

  EmailMessage emailMessage = Email.CreateMessage();
  emailMessage.Recipients = Email.CreateRecipients("someone@email.com");

Subject
~~~~~~~
- **Stores type:** String
- **Effect:** Sets the subject of the email message

Sample::

  EmailMessage emailMessage = Email.CreateMessage();
  emailMessage.Subject = "CREATE WEALTH! 10 TIPS FOR BECOMING A MILLIONAIRE IN MONTHS!";

Email.CreateMessage
---------------------
Creates a new email message.

Overloads
~~~~~~~~~
1. **Email.CreateMessage(): EmailMessage**

Usage::

  EmailMessage emailMessage = Email.CreateMessage();

Email.CreateRecipient
-----------------------
Creates a recipient to add to an email message.

Overloads
~~~~~~~~~~
1. **Email.CreateRecipients(Object address, RecipientType recipientType): EmailRecipient**

- value is an EmailAddress or String

Sample::

  String recipient = "someone@gmail.com";
  emailMessage.Recipients = Email.CreateRecipient();


Email.CreateRecipients
------------------------
Creates recipients to add to an email message.

Overloads
~~~~~~~~~
1. **Email.CreateRecipients(params Object[] values): EmailRecipient[]**

- values may be of type EmailAddress, EmailRecipient, or String

Sample::

  String recipient1 = "somebody@gmail.com";
  String recipient2 = "someoneelse@gmail.com";
  emailMessage.Recipients = Email.CreateRecipients(recipient1, recipient2);