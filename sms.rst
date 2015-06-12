Sms
===

Sms.CreateMessage
-----------------
Creates a new SMS message with a blank body, no recipients, no reply to email address, and no subject.

Overloads
~~~~~~~~~~
1. **Sms.CreateMessage(): SmsMessage**

Sample::

  SmsMessage smsMessage = Sms.CreateMessage();
  smsMessage.Body = @"Hi #{record.Name}, this is a test SMS.";
  smsMessage.Recipients = Sms.CreateRecipients(record.Mobile);
  smsMessage.ReplyTo = EmailAddress.Parse('support@irwinsolutions.com');
  smsMessage.Subject = "Test SMS";

Sms.CreateRecipients
--------------------
Creates SMS recipients to set as recipients for an SMS message.

Overloads
~~~~~~~~~
1. **Sms.CreateRecipients(params Object[] values): SmsRecipient[]**

- values should be a collection of strings corresponding representing phone numbers or possible phone numbers