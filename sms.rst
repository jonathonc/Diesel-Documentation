Sms
===

Typical Usage
-------------
::

  Record[] smsRecords = records.Where(record -> record.Mobile != null && record.Email == null);
  ForEach(smsRecords, record -> {
    SmsMessage smsMessage = Sms.CreateMessage();
    smsMessage.Subject = "#{dealershipName} - #{processName} SMS (Rego: #{record.Rego})";
    smsMessage.ReplyTo = EmailAddress.Parse("service@someDealership.com");
    smsMessage.Body = "@Dear #{record.NameSMS}. Your #{record.MakeSMS} #{record.Rego} service appointment is confirmed for: #{record.ApptDate}, from 7.30am. On the day of your service, please bring the following: Driver's License, Service Book and All Vehicle Keys. Rgds #{dealershipName} (#{dealershipPhone}).";
    smsMessage.Concatenation = true;

    messageList = messageList.Add(smsMessage);
  })

Properties
----------

Body
~~~~
- **Stores type:** String
- **Effect:** Sets SMS message body

Sample::

  SmsMessage smsMessage = Sms.CreateMessage();
  smsMessage.Body = "@Dear #{record.NameSMS}. Your #{record.MakeSMS} #{record.Rego} service appointment is confirmed for: #{record.ApptDate}, from 7.30am. Rgds #{dealershipName} (#{dealershipPhone}).";

Concatenation
~~~~~~~~~~~~~
- **Stores type:** Bool
- **Effect:** Sets whether long SMS messages should be concatenated

Sample::

  SmsMessage smsMessage = Sms.CreateMessage();
  smsMessage.Body = "@Dear #{record.NameSMS}. Your #{record.MakeSMS} #{record.Rego} service appointment is confirmed for: #{record.ApptDate}, from 7.30am. On the day of your service, please bring the following: Driver's License, Service Book and All Vehicle Keys. Rgds #{dealershipName} (#{dealershipPhone}).";
  smsMessage.Concatenation = true;

DeliveryDate
~~~~~~~~~~~~
- **Stores type:** DateTime
- **Effect:** Sets the delivery date of the SMS message. Not normally used. May have strange behaviour. Ask Jonathon Choo.

Encoding
~~~~~~~~
- **Stores type:** String
- **Effect:** Sets the encoding of the SMS message.

Possible values:

- "Gsm7"
- "Gsm8"
- "Utf16"

Sample::

  SmsMessage smsMessage = Sms.CreateMessage();
  smsMessage.Encoding = "Gsm7";

ExpiryDate
~~~~~~~~~~
- **Stores type:** DateTime
- **Effect:** Sets the expiration date of the SMS message. If it is not sent out before the expiration date, it will not be sent at all.

Id
~~
- **Stores type:** Int
- **Effect:** Sets message ID number

Recipients
~~~~~~~~~~
- **Stores type:** SmsRecipient or SmsRecipient[]
- **Effect:** Sets the recipient of the SMS message

Sample::

  SmsMessage smsMessage = Sms.CreateMessage();
  smsMessage.Recipients = Sms.CreateRecipients(record.Mobile);

ReplyTo
~~~~~~~
- **Stores type:** EmailAddress
- **Effect:** Sets the email address that replies will be sent to

Sample::

  SmsMessage smsMessage = Sms.CreateMessage();
  smsMessage.ReplyTo = EmailAddress.Parse("service@someDealership.com");

Subject
~~~~~~~
- **Stores type:** String
- **Effect:** Sets the subject of the SMS. Cannot actually be read by the SMS recipient but useful for tracking and for email notifications.

Sample::

  SmsMessage smsMessage = Sms.CreateMessage();
  smsMessage.Subject = "#{dealershipName} #{processName} SMS (Rego: #{record.Rego})";

Tag
~~~
- **Stores type:** Tag
- **Effect:** Adds a tag to the SMS message

Sample::

  Object[] originalData = Collection.Create(record);
  originalData = originalData.Map(message -> message to Record);
  String csv = Csv.CreateWithDefaults(originalData to Record[],
      data -> 'Name': data.Name,
      data -> 'Model': data.Model,
      data -> 'Make': data.Make,
      data -> 'Rego': data.Rego,
      data -> 'Mobile': data.Mobile
  );
  
  SmsMessage smsMessage = Sms.CreateMessage();
  smsMessage.Tag["Original"] = Tag.CreateData('CSV', csv);

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