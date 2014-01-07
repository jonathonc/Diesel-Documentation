Sample Code
===========

SMS
---

.. code-block:: ruby
    :linenos:

    // Sets the language settings.
    Settings.Data.CaseInsensitiveFieldNames = true;
    Settings.Data.ConvertDbNullToNull = true;
    Settings.Data.ConvertNullToEmptyString = true;
    Settings.Data.TrimFieldNames = true;
    Settings.Data.TrimStrings = true;
    Settings.Locale.NumericFormat = NumberFormats.General;
    Settings.Locale.TemporalFormat = "{0}";
    Settings.Locale.Culture = Culture.Get('en-AU');
    Settings.Locale.PhoneNumberParser = PhoneNumber.GetParser('AUS/Mobile');
    Settings.Locale.TimeZone = Time.GetTimeZone('SYD');
     
    // Columns
    Record[] records = Data['Source'] to Record[];
    Record firstRecord = records.First();
    Object mobile = firstRecord['Mobile'];
    Object name = firstRecord['Name'];
     
    // Fields
    Object Mobile = TryConvert.ToPhoneNumber(mobile);
    Object CSV = Csv.AutoCreate(
        records, 
        Csv.GetFieldDelimiter('Comma'), Csv.GetRecordDelimiter('CRLF'), Csv.GetQualifier('SingleQuote'), String.GetEncoding('us-ascii'));
     
    // SMS Template
    SmsMessage smsMessage = Sms.CreateMessage();
    smsMessage.ReplyTo = Convert.ToEmailAddress("testing@irwinsolutions.com");
    smsMessage.Subject = "Test Message";
    smsMessage.Body = "A test message from Hg+";
    smsMessage.Recipients = Sms.CreateRecipients(Mobile);
    smsMessage.Encoding = Sms.GetEncoding("Gsm7");
    smsMessage.Condition = Mobile != null;
    smsMessage.Tag["Source"] = "{" + "dataType: 'CSV',  data : '#{CSV}'" + "}";

Email
-----

.. code-block:: ruby
    :linenos:
    
    // Sets the language settings.
    Settings.Data.CaseInsensitiveFieldNames = true;
    Settings.Data.ConvertDbNullToNull = true;
    Settings.Data.ConvertNullToEmptyString = true;
    Settings.Data.ConvertToString = true;
    Settings.Data.TrimFieldNames = true;
    Settings.Data.TrimStrings = true;
    Settings.Locale.NumericFormat = NumberFormats.General;
    Settings.Locale.TemporalFormat = "{0}";
    Settings.Locale.Culture = Culture.Get('en-AU');
    Settings.Locale.PhoneNumberParser = PhoneNumber.GetParser('AUS/Mobile');
    Settings.Locale.TimeZone = Time.GetTimeZone('SYD');
     
    Object EmailAddress = TryConvert.ToEmailAddress(Data.Source['Email']);
     
    // Email Template
    Recipient{Email} recipient1 = Email.CreateRecipient(EmailAddress);
    Message{Email} emailMessage = Email.CreateMessage();
    emailMessage.From =  Convert.ToEmailAddress("support@irwinsolutions.com");
    emailMessage.Subject = "Subject Goes Here";
    emailMessage.Body = @"Body Goes Here";
    emailMessage.Recipients = Email.CreateRecipients(recipient1);
    emailMessage.Condition = EmailAddress != null;