Object: Email
=============

CreateMessage()
---------------

Creates an EmailMessage object

::

  EmailMessage : Email.CreateMessage()

Sample Code
~~~~~~~~~~~

.. code-block:: ruby
  
  EmailMessage emailMessage = Email.CreateMessage();
  emailMessage.Body = "the message body";
  emailMessage.Subject = "the subject goes here.";

CreateRecipient()
-----------------

Creates an EmailRecipient object

CreateRecipient(Address address)
--------------------------------

Creates an EmailRecipient object

CreateRecipient(Address address, EmailRecipientType recipientType)
-------------------------------------------------------------------

Creates an EmailRecipient object


CreateRecipients(params Address[])
-----------------------------------


GetRecipientType(string)
------------------------

Creates an EmailRecipientTye object. Only the following values can be used 'To', 'Cc', 'Bcc'
can be used for **type**.

::

  EmailRecipientType : Email.GetRecipientType(string type)