Sms
===

Sms.CreateMessage
=================

**Usage**

```
SmsMessage smsMessage = Sms.CreateMessage();
smsMessage.Body = @"Hi #{record.Name}, this is test SMS.";
smsMessage.Encoding = Sms.GetEncoding("Gsm7");
smsMessage.Recipients = Sms.CreateRecipients(record.Mobile);
smsMessage.ReplyTo = EmailAddress.Parse('support@irwinsolutions.com');
smsMessage.Subject = "Test SMS";
```