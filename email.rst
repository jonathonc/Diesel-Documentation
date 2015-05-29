Email
=====

Email.CreateMessage()
---------------------
Creates a new email message.

Overloads
~~~~~~~~~
1. **Email.CreateMessage(): EmailMessage**

Usage::

  EmailMessage emailMessage = Email.CreateMessage();

Email.CreateRecipient()
-----------------------
Creates a recipient to add to an email message.

Overloads
~~~~~~~~~~
1. **Email.CreateRecipients(Object address, RecipientType recipientType): EmailRecipient**

- value is an EmailAddress or String

Sample::

  String recipient = "someone@gmail.com";
  emailMessage.Recipients = Email.CreateRecipient();


Email.CreateRecipients()
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