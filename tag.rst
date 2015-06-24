Tag
===

A metadata tag commonly applied to messages.

Tag.CreateData
--------------
Returns a JSON String which represents the object containing the specified data type and data.

Overloads
~~~~~~~~~
1. **Tag.CreateData(String dataType, String data): String**

Sample::

  // SMS
  Record[] smsRecords = records.Where(record -> record.Mobile != null);
  ForEach(smsRecords, record -> {
      
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
      smsMessage.Subject = "Post Service Follow Up - #{record.Rego} #{record.Name}";
      smsMessage.Body = @"TEST: Dear #{record.Name}, Did you know camels have three eyelids to protect themselves from blowing sand? Rgds, #{dealershipName}";
      smsMessage.Recipients = Sms.CreateRecipients(record.Mobile);
      smsMessage.Concatenation = true;
      smsMessage.Tag["Original"] = Tag.CreateData('CSV', csv);
      
      messageList = messageList.Add(smsMessage);
  });