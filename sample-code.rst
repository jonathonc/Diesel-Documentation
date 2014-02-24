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
    Settings.Locale.UtcOffset = Time.GetTimeZone('AUS/Sydney');     

    Object[] messages = Collection.Create();
    Record[] records = Data['Source'] to Record[];
    
    Record[] cleansedRecords = records.Select(
        record -> 'Name' : record['Name'],
        record -> 'ParsedMobile' : PhoneNumber.TryParse(record['Mobile'] to String));
        
    Record[] filteredRecords = cleansedRecords.Where(record -> record['ParsedMobile'] != null);
    
    filteredRecords.Each(record -> {
        SmsMessage smsMessage = Sms.CreateMessage();
        smsMessage.Body = @"test";
        smsMessage.Concatenation = false;
        smsMessage.Encoding = Sms.GetEncoding("Gsm7");
        smsMessage.Recipients = Sms.CreateRecipients(record['ParsedMobile']);
        smsMessage.ReplyTo = EmailAddress.Parse('jonathonc@irwinsolutions.com');
        smsMessage.Subject = "test";

        messages = messages.Concat(Collection.Create(smsMessage));
    });

    Dispatch(messages.SelectSingle(message -> message to Message));

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