#Send SMS
##delivery.sendSMS

**Drag and drop this block from the delivery package.**

**Use Case:** Send an SMS to a new registered user.

**Parameters information:**

Parameter | Use | Description
--------- | ------- | -----------
Message | Plain Text or use #body parameter [(How to?)](#body-parameters) | This text will be sent as a text message  |
To | Phone Number + Area Code or use #body parameter [(How to?)](#body-parameters) | Use a sentence that describes the email. For example: Welcome to RapidAPI.


**Returns Examples:** Success or Error.

**How to test?** Use the 'RUN' tool [(How to?)](#run-tool)

<aside class="warning">Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
Success — Use the **response.SendMessage** block to get a success message back. In the message field, use the #[Name of the object] to get it.
</aside>


#Send Email
##delivery.sendPlainEmail

**Drag and drop this block from the delivery package.**


**Use Case:** Can be part of every scheme. For example: User has signed up and a welcome email has been sent to him.

**Parameters information:**

Parameter | Use | Description
--------- | ------- | -----------
From | Use an email address or use #body parameter [(How to?)](#body-parameters) | This will be shown as the sender email address  |
Subject | Plain text or use #body parameter [(How to?)](#body-parameters) | Use a sentence that describes the email. For example: Welcome to RapidAPI.
Text | Plain Text | Use the text that will be sended in the email body.
To | Use an email address or use #body parameter [(How to?)](##body-parameters) | Who's going to get this email?

**Returns Examples:** Success or Error.

**How to test?** Use the 'RUN' tool [(How to?)](#run-tool)

<aside class="warning">Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">

- Use response.sendMessage block,
- Message = Success
- Status = 200 (Success).
</aside>
