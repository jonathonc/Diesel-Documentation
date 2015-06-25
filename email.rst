Email
=====

Typical Usage
-------------

External Email
~~~~~~~~~~~~~~
::

  Record[] emailRecords = records.Where(record -> record.Email != null);
  ForEach(emailRecords, record -> {
    EmailMessage emailMessage = Email.CreateMessage();
    emailMessage.Subject = "#{dealershipName} #{processName} for Rego:#{record.Rego} (#{record.ApptDate})";
    emailMessage.Body = @"";
    emailMessage.From = EmailAddress.Parse(replyToEmail);
    emailMessage.Recipients = Email.CreateRecipients(record.Email);

    messageList = messageList.Add(emailMessage);
  });

Internal Email
~~~~~~~~~~~~~~
::

  EmailMessage internalEmailMessage = Email.CreateMessage();
  internalEmailMessage.Attachments = Collection.Create(noContactCsv).Map(x -> x to File);
  internalEmailMessage.From =  EmailAddress.Parse("support@irwinsolutions.com");
  internalEmailMessage.Subject = "Appointment Confirmation - No Contact Email";
  internalEmailMessage.Body = @"
  <html xmlns=http://www.w3.org/1999/xhtml><head><title>irwinSolutions</title><style type=text/css>table{font-family:Verdana;border-collapse:collapse;border-spacing:0;border:none;color:#000}table tr{padding:15px 40px 15px 40px}body{font-family:Verdana;font-size:12px}img{border:0 #FFF}p{margin-bottom:1em}.style1{width:650px;border-collapse:collapse;background-color:#fff;color:#000;font-size:12px}.footer{font-family:Verdana;font-size:11px;color:#de0000;text-align:center;padding:30px}.footer a{color:#de0000}.pad{padding:10px 30px 10px 30px}.font{font-size:12px}.irwin{color:#999;font-size:7.5pt;font-family:Verdana,sans-serif}.B{font-weight:700;color:#000;font-size:12px}.title{font-size:12px;font-weight:700;line-height:20px}.irwins{font-size:7pt;color:#999;font-family:Verdana,sans-serif}.blue{color:#00f}.under{text-decoration:underline}a:link{color:#de0000}a:visited{color:#de0000}a:hover{color:#de0000}a:active{color:#de0000}</style><body><table cellpadding=0 class=style1 style=border-collapse:collapse;font-family:Verdana;size:10px;color:#000><tr><td class=pad><p>Hi,<br><br></p><p>Your daily Service Booking Confirmation has been processed successfully. A total of #{ValidRecords} valid records was processed by Mercurion.<br>- #{SentEmails} Emails were Sent<br>- #{SentMobiles} Mobiles were Sent</p><p>Please also find attached:<br>- a listing of customers that were not contacted as their record did not contain a valid mobile number or email address</p><p><span class='irwin B'>Regards<br>irwinSolutions Support<br><br><br><img src=http://h.messagesmart.com/IrwinSolutions/logo.jpg border=0 style='border:none;max-width:100%'></span></p><p><span class=irwin>Level 7, 65 York Street<br>Sydney NSW 2000 Australia<br>Ph (Aus): (02) 9262 6544<br>Ph (Int): +61 2 9262 6544<br>Fax: +61 2 9475 0186</span></p><tr><td class=pad><p class=irwins>DISCLAIMER: 1) CONFIDENTIALITY: This email is confidential and contains privileged or copyright information. You may not present this message to another party without consent from the sender. If you are not the intended recipient please notify the sender and delete this email, and be aware that you are bound to confidentiality, may not copy, distribute or use this email. 2) LIABILITY: This email is not a binding agreement and does not conclude an agreement without the express confirmation by the sender's superior or a director of the Company. 3) VIRUSES: The Company does not guarantee this email is free of viruses or defects. 4) ADVICE: This email is the view/opinion of the sender and must not be construed as advice. Any actions taken on the basis of this email are at the reader's own risk. The sender of this email is expressly required not make any defamatory statements or infringe any copyright or any other legal right and shall be held responsible for any arising damages or liability.</p></table>
  ";
  internalEmailMessage.Recipients = Email.CreateRecipients(internalRecipient);
  messageList = messageList.Add(internalEmailMessage);

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