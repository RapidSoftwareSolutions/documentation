#Database
Here you will get an explanation about the backend functions connected to

![](http://i.giphy.com/l3Ts3QZR8xVCdKi5y.gif)

##Database Find.one
**Name of the backend functions:** Find One object in your database.

**Use Case:** Let’s say you want to get an object from your database. For example: Get user’s email.

**Parameters information:**


Parameter | Use | Example
--------- | ------- | -----------
Collection | This is the collection you’ve created on the database section. If you didn’t created any… just give it a name and a collection will be created (Yes! MongoDB).  | users  |
Query Field | Where do you want to find the data? | you want to get an email - Use the string = email.
Query Operator | What will be the search type (action) that will go over your database. | ...
Query Value | What are you looking for? | the exact email: mickey@rapidapi.com
To | Object This will show the result, give it a name and use with '#' to get the result as a response later on.| result
<aside class="warning">Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
Success — Use the **response.SendMessage** block to get a success message back. In the message field, use the #[Name of the object] to get it. In this case, it will be: #result
</aside>

**Missing:** Use the **response.SendMessage** block to get a missing message back. For example: The object is missing.


##Database.find
**Name of the backend functions:** Find more than one object in your database.

**Use Case:** Let’s say I want to get all the data in a specific collection.

**Parameters information:**


Parameter | Use | Example
--------- | ------- | -----------
Collection | This is the collection you’ve created on the database section. If you didn’t created any… just give it a name and a collection will be created (Yes! MongoDB).  | users  |
Query Field | Where do you want to find the data? | you want to get an email - Use the string = email.
Query Operator | What will be the search type (action) that will go over your database. | ...
Query Value | What are you looking for? | the exact email: mickey@rapidapi.com
To | Object This will show the result, give it a name and use with '#' to get the result as a response later on.| result
<aside class="warning">Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
Success — Use the **response.SendMessage** block to get a success message back. In the message field, use the #[Name of the object] to get it. In this case, it will be: #result
</aside>

**Missing:** Use the **response.SendMessage** block to get a missing message back. For example: The object is missing.

##Database.update
**Name of the backend functions:** Update an existing object in a collection.

**Use Case:** update user's email or password.

**Structure:** Use the query to find what you want to update and then use the update section to actually update it.


**Parameters information:**


Parameter | Use | Example
--------- | ------- | -----------
Collection | This is the collection you’ve created on the database section. If you didn’t created any… just give it a name and a collection will be created (Yes! MongoDB).  | users  |
Query Field | Where do you want to find the data? | you want to get an email - Use the string = email.
Query Operator | What will be the search type (action) that will go over your database. | ...
Query Value | What are you looking for? | the exact email: mickey@rapidapi.com


<aside class="warning">Error - For Example: Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
Success — For Example: Use the **response.SendMessage** block to get a success message back. In the message field, use the #[Name of the object] to get it. In this case, it will be: #result.
</aside>

##Database.save

![](http://i.giphy.com/3o6ozGZ0eUbk0onFte.gif)

**Name of the backend functions:** Save an object in a collection

**Use Case:** You want to save a new customer type that has registered to your online store.

**How To Use (DOC):**

1. Click add to add a key.

2. Name your key and choose the object type you want to use.

2.a. Array is a collection of values. Use this to save a collection of users IDs.

2.b. Object is a custom data schema that can contain arrays and strings and more objects.

3.c. String is traditionally a sequence of characters. Use it to define key and value for something you want to save in the database.


<aside class="warning">Error - For Example: Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
Success — For Example: Use the **response.SendMessage** block to get a success message back.
</aside>

##Database.remove
**Name of the backend functions:** Remove an object in a collection

**Use Case:** You want to remove a customer type from your collection.



**Parameters information:**


Parameter | Use | Example
--------- | ------- | -----------
Collection | This is the collection you’ve created on the database section. If you didn’t created any… just give it a name and a collection will be created (Yes! MongoDB).  | users  |
Query Field | Where do you want to find the data? | you want to get an email - Use the string = email.
Query Operator | What will be the search type (action) that will go over your database. | ...
Query Value | What are you looking for? | the exact email: mickey@rapidapi.com


<aside class="warning">Error - For Example: Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
Success — For Example: Use the **response.SendMessage** block to get a success message back.
</aside>
