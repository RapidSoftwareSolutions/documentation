#Files
##File.save

**Name of the backend functions:** Save file on the server

**Use Case:** User want to add a profile picture.

**How to use:** Add an upload function in your code and connect the endpoint to it.

**Parameters information:**

Parameter | Use | Description
--------- | ------- | -----------
File | #body.image | use #body parameter [(How to?)](#body-parameters) to upload file|
Folder | #body.images | The folder that will contain all the files.
Key | profilepic | the name of the file you want to upload.

**Returns Examples:** Success or Error.

**How to test?** Use the 'RUN' tool [(How to?)](#run-tool)

<aside class="warning">Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">

- Use response.sendMessage block,
- Message = Success
- Status = 200 (Success).
</aside>

##File.files.saveWithRandomKey

**Name of the backend functions:** Save file on the server and giving it a different name.

**Use Case:** You want to add gallery to your website.

**How to use:** Add an upload function in your code to connect our endpoint to it.

**Parameters information:**

Parameter | Use | Description
--------- | ------- | -----------
File | #body.image | use #body parameter [(How to?)](#body-parameters) to upload file|
Folder | #body.images | The folder that will contain all the files.
to | object | where do you want to save the file? Give it a name.

**Returns Examples:** Success or Error.

**How to test?** Use the 'RUN' tool [(How to?)](#run-tool)

<aside class="warning">
For Example:
Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
For Example:
- Use response.sendMessage block,
- Message = Success
- Status = 200 (Success).
</aside>

##files.getDownloadURL

**Name of the backend functions:** Get a url of an uploaded file.

**Use Case:** Can be used with an uploader to get the link to the file you’ve uploaded.

**Parameters information:**

Parameter | Use | Description
--------- | ------- | -----------
folder | #body.image | from what folder do you want to get the file URL from? |
key | #body.images | What’s the name of the file?
to | object | where do you want to save the file? Give it a name.

**Returns Examples:** Success or Error.

**How to test?** Use the 'RUN' tool [(How to?)](#run-tool)

<aside class="warning">
For Example:
Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
For Example:
- Use response.sendMessage block,
- Message = Success
- Status = 200 (Success).
</aside>

##files.read

**Name of the backend functions:** Read a file.

**Use Case:** Allows you to read the file and to show it. Let’s say you want to show an image on the screen.

**Parameters information:**

Parameter | Use | Description
--------- | ------- | -----------
folder | #body.image | from what folder do you want to get the file URL from? |
key | #body.images | What’s the name of the file?
to | object | where do you want to save the file? Give it a name.

**Returns Examples:** Success or Error.

**How to test?** Use the 'RUN' tool [(How to?)](#run-tool)

<aside class="warning">
For Example:
Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
For Example:
- Use response.sendMessage block,
- Message = Success
- Status = 200 (Success).
</aside>
