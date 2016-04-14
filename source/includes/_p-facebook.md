#Facebook
##Facebook.Login
**Drag and drop this block from the Facebook Package.**

**The Endpoint Must Be in a `GET` method:** To add a facebook login endpoint, go to the endpoint page and create new endpoint, while creating, click on 'advanced settings' and change the endpoint type to a `GET` type.

**Use Case:** Add a facebook login plugin to your app.


**Parameters information:**

Parameter | Use | Description
--------- | ------- | -----------
Client ID | Your App ID on [Facebook Developers](https://developers.facebook.com/) | What is your app ID?   |
Client Secret | Your App Secret on [Facebook Developers](https://developers.facebook.com/) | What is your app ID?
To | Object | Give your object a name, so you can print it later with the result.

**Returns Examples:** Login url.

**How to test?** Use the 'RUN' tool [(How to?)](#run-tool)

<aside class="warning">Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">

- Use response.sendMessage block,
- Message = #[object name].
- Status = 200 (Success).
</aside>


##facebook.getUserDetails
**Drag and drop this block from the Facebook Package.**

**Use Case:** Get details of a user that has signed up using your facebook app.


**Parameters information:**

Parameter | Use | Description
--------- | ------- | -----------
userToken | [Facebook Access Token Tool ](https://developers.facebook.com/tools/accesstoken/) | What's the user's token? |
App Secret | Your App Secret on [Facebook Developers](https://developers.facebook.com/) | What is your app ID?
To | Object | Give your object a name, so you can print it later with the result.

**Returns Examples:** Login url.

**How to test?** Use the 'RUN' tool [(How to?)](#run-tool)

And use the [AccessToken](https://developers.facebook.com/tools/accesstoken/) Tool on Facebook.

<aside class="warning">Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">

- Use response.sendMessage block,
- Message = #[object name].
- Status = 200 (Success).
</aside>

##facebook.postonWall
**Drag and drop this block from the Facebook Package.**

**Use Case:** Post on user's wall.

**Parameters information:**

Parameter | Use | Description
--------- | ------- | -----------
Message | Plain Text or #Body Parameter [(How to?)](##body-parameters) | What is the message that will be published on user's wall|
userToken | [Facebook Access Token Tool ](https://developers.facebook.com/tools/accesstoken/) | What's the user's token? |
To | Object | Give your object a name, so you can print it later with the result.

**Returns Examples:** Login url.

**How to test?** Use the 'RUN' tool [(How to?)](#run-tool)

And use the [AccessToken](https://developers.facebook.com/tools/accesstoken/) Tool on Facebook.

<aside class="warning">Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">

- Use response.sendMessage block,
- Message = #[object name].
- Status = 200 (Success).
</aside>

