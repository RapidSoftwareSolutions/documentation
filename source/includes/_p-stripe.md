#Stripe (Payment)
##Stripe.charge

**The Endpoint Must Be in a `GET` method:** To add a stripe charge function => endpoint, go to the endpoint page and create new endpoint, while creating, click on 'advanced settings' and change the endpoint type to a `GET` type.

**Name of the backend functions:** Charge trough Stripe.

**Use Case:** Sell items trough your website, charge using stripe.

**Parameters information:**

Parameter | Use | Description
--------- | ------- | -----------
amount | For example: 32.075001| Use generater or Google Maps to get lat |
currency | For example: 34.783453 | Use generater or Google Maps to get long
description | Use numbers | In meters. For example: 50 meters.
secretId | object | where do you want to save the file? Give it a name. For example: places
source | object | where do you want to save the file? Give it a name. For example: places

<aside class="warning">
For Example:
Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
For Example:
- Use response.sendMessage block,
- Message = Use the object you have used in the 'to' field to print the result. In this case we used #places
- Status = 200 (Success).
</aside>
