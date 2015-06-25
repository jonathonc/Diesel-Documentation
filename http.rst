HTTP
====

A HTTP request.

Typical Usage
-------------
::

  HttpMessage httpMessage = Http.CreateMessage();
  httpMessage.Body = PolarBear.CreatePayload(projectId, 
    originalRecord.Name to String, originalRecord.Mobile to String, originalRecord.Rego to String, record.Reply to String, description,
        'SMS Message' : record.OriginalMessage,
        'SMS Message Timestamp' : originalMessageTimestampText,
        'Model' : originalRecord.Model,
        'Make' : originalRecord.Make,
        'Rego' : originalRecord.Rego
    );
  HttpRecipient httpRecipient = Http.CreateRecipient();
  httpRecipient.UserName = polarBearApiKey;
  httpRecipient.Address = UriAddress.Parse(polarBearApiUrl);
  httpMessage.Recipients = Http.CreateRecipients(httpRecipient);
  
  messages = messages.Add(httpMessage);

HttpRecipient Properties
-------------------------

UserName
~~~~~~~~~
- **Stores type:** String
- **Effect:** Sets the username of the recipient

Address
~~~~~~~

- **Stores type:** UriAddress
- **Effect:** Sets the URI address of the recipient


HttpMessage Properties
----------------------

Recipients
~~~~~~~~~~
- **Stores type:** HttpRecipient
- **Effect:** Sets the recipient for this HTTP message

Http.CreateRecipient
--------------------
Creates a HttpRecipient object. Often used in conjunction with Http.CreateRecipients.

Overloads
~~~~~~~~~
1. **Http.CreateRecipient(): HttpRecipient**

Http.CreateRecipients
---------------------
Converts one or more objects representing HTTP recipients to HttpRecipients.

Overloads
~~~~~~~~~
1. **Http.CreateRecipients(params[] Object): HttpRecipient[]**

Http.CreateMessage
-------------------
Creates a new empty HTTP message.

Overloads
~~~~~~~~~
1. **Http.CreateMessage()**

Sample::

  HttpMessage httpMessage = Http.CreateMessage();