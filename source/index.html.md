---
title: RapidAPI Documentation 

language_tabs:
  - Web
  - iOS
  - Android

toc_footers:
  - <a href='https://www.rapidapi.com/'>Sign Up</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to RapidAPI. RapidAPI let's you build the backend for your app easily - without writing a single line of code. With RapidAPI you can use blocks to construct your backend logic. From saving to a database to proccesing payments - blocks can do anything!

![](https://scontent-fra3-1.xx.fbcdn.net/hphotos-xfa1/v/t1.0-9/12931066_10209313487584400_8906391932503995637_n.jpg?oh=514fe8636ab0c86e503dd8bbff92b599&oe=57BB2781)


##How it's all started?

We were at a hackathon when we realized all the teams were spending hours building the same backend logic: installing DBs, writing user signup logic, updating packages and more. All these teams were spending hours and hours - basically doing the same thing. That's what we've built RapidAPI for. With RapidAPI, you get all the basic backend functions deliverd to you as blocks. All you have to do is drag and drop them and you get a fully functional backend - hosted in the cloud. **Rather than spending days on backend development - do it in minutes**.

##The Backend
RapidAPI is an online platform that lets you create a back end for your web or mobile app without writing a single line of code. Every web or mobile app has two parts:

- Front end: Runs on the user's device. In charge of showing the user interface (UI) and reacting to the users actions. For example: showing a button and then reacting to a click on it.
- Back end: Runs on servers. In charge of storing data (e.g. user details, product lists, etc...) and performing actions (authenticating users, sending push notifications, etc...).

When using RapidAPI, you construct the back end logic using blocks. Each block represents a basic action done in the back end. These are things like saving to a database, sending a notification or accessing an API. The back end is hosted on the RapidAPI servers and you can use it from your app.

##How it works

Your backend is built out of backend actions. Each action performs a certain task for your app. Examples of actions can be:

- **Sign up**: register a user to your app.
- **Sign in**: verify a user in your app.
- **Send message**: send a message from one user to another in your app.
- **Purchase product**: pay for a product and mark it as purchased in your app.

Each one of these backend actions is built out of blocks. Each block performs a basic task within an action. Let's take a sign up action for example. We'll first want to make sure that the user sends a valid email address. For that, we'll use the _verify.email_ block. This block will get the email passed in the request to that action and check if it's valid. It'll have 2 outcomes - these are things that can happen - either the email is valid, or it's not. If it's not - we'll return an error message. If it is, we'll check the password using a similar _verify.passwordLength_ block. If that's valid, we'll save to the database - and so on... That way, we'll build the logic of the action. It'll end up looking like that:

![](http://curious-warthog-bhhb.imrapid.io/basic_block_flow.jpg)

#Getting started
Let's create the basic sign up backend action the get the ropes of using the system.

To begin, head over to [https://rapidapi.com](https://rapidapi.com) and sign up.

##Creating your first project

A project in RapidAPI is basically the backend of a single app. It contains all the backend actions for that app, as well as it's database. Let's start by creating a new project.

![](http://i.giphy.com/3o6ozxLj7NXDnZzK4U.gif)

##Creating a database collection

Now that we have a project, create a database collection that will store all the users that sign up. Do so by heading over to the database tab and clicking _Create New Collection_. Name the collection _users_ and create it.

You'll now notice you have a fully functional database collection. In our next step, we'll build a backend action that saves to it.

![](http://i.giphy.com/l3V0pRF2XJ6nl0Hok.gif)

##Creating the Sign Up backend action

To create the sign up backend action head over to the _ENDPOINTS_ tab. Click the _Backend Action_ button and create the new backend action named _sign up_. Once it is created, open it by clicking _Edit_.

![](http://i.giphy.com/3o6ozunG5Pw2Z7iwMw.gif)

Within the editor, we'll first drag in the _verify.email_ block to verify that the email supplied by the user is correct. As the parameter to be checked, we'll use `#body.email`. This will be replaced with the value sent under 'email' in the call to that backend action.

![](http://i.giphy.com/xT1XGJHxpYuuZ71iuI.gif)

<aside class="notice">
Your application can pass parameters to the backend action in the request body. Parameters are passed as key-value pairs. For example, you can pass a username in the request body under the key `username`. To access it, use `#body.username` just like we did with the email just before.
</aside>

You'll notice that the verify block has 2 outcomes:

- **is**: The passed value is a valid email.
- **not**: The passed value is not a valid email.

If it's not a valid email, we'll use the _response.sendMessage_ block to send back an error message saying `The email sent is not valid`, with a 400 code.

<aside class="notice">
Every backend action must end with a response. This response should let the app know what happened (success, error, etc...). Sometimes we'll send data in the response (for example, a feed of posts or a string of messages).
Every response has a status code signifying the status of the request (you may be familiar with 404 which means not found). You can see a drop down with popular response codes.
</aside>

![](http://i.giphy.com/3o6ozjsuyiwOzLYrL2.gif)

In case of success we will want to save the new user (e.g. email address) to the database (in real life we will probably get a password and name and want to verify them, but it's a very similar proccess).

For that we will drag in the _database.save_ block which saves a new row into the database. We will set it to save to the `users` collection we've created earlier and define a row with one column - email. The value will be `#body.email` - the same value we verified in the previous step.

![](http://i.giphy.com/d3FzTwod8PETNqNi.gif)

You may notice the _database.save_ block has 2 possible outcomes: success and error. In both cases we'll use the _response.sendMessage_ block:

- **success**: we'll send an `OK` message with a 201 status code (201 usually stands for "record created").
- **error**: we'll send a `Server error` message with a 500 status code (500 usually means "server error").

![](http://i.giphy.com/d3FyDFl05q5FUbQc.gif)

You by now have a fully working sign up backend action. Next up we'll try it up and see how it can be connected to a mobile / web app.

##Trying it out

Now that you are the proud owner of a backend action, you will probably want to take it to a spin and see how it works, right? To do just that you can use the _run_ button on the top right corner of the editor. It'll open up the run panel. You should go to the body tab where we can set the body parameters. Create an `email` parameter and put a valid email in it. Press run and you'll see the success message.

![](http://i.giphy.com/26AHHJYBW3sWQMCTm.gif)

You can also go back to the database tab in the project page and see the new email saved to the _users_ collection. You can also try putting an invalid email and see that you are getting the appropriate error message.

##Implementing it in your app

Every backend action in RapidAPI is in-fact an HTTP endpoint. That means that you can make requests to it from any platfrom (including iOS, Android and Web Pages) using standard HTTP Request frameworks.

<aside class="notice">
HTTP is a protocol used for communication with web servers. Web pages are offered using the HTTP protocol (hence the `http://` in the beggining of web page addresses. You can learn more about it [here](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) .
</aside>

To make life easier, we have compiled pre written code snippets that connect to the backend actions. To access them, go back to the Endpoints tab in the project page, select the backend action that you want to connect to and click on the Code Snippet button. In the popup, select the platform and proggraming languge and copy the code snippet.

![](http://i.giphy.com/26AHKFF6SkVucF9N6.gif)

Notice that if you are using `#body.SOMETHING` in your action, the code snippet will have that `SOMETHING` in place already, so you'll just need to replace it's value.

Here are some more in-depth guides on mobile integrations:

- **iOS** - [iOS Swift integration tutorial](https://github.com/RapidSoftwareSolutions/ios-swift-integration-tutorial).


#System Overview
## Overview Page 
The overview page will show you the following information:

- Number of Backend Actions (Endpoints), Numbers (For sending SMS messages), And Databases you've used in your project.
- Basic Tutorials.
- Collaborators - Here you can share your project with other teammates. 
- Your Latest Activity.
- Basic Statistics.

## Endpoints Page
The endpoints page is the core of your app. Through this page you can create the backend actions for your app, create static pages based on HTML, CSS and JS and upload files. 

![](http://i.giphy.com/l0LJdmkawpJ1lnzpK.gif)

###Web Pages

By clicking on Web Pages you will be able to create a static webpage that will be host on our servers. **The URL of the web page will be structured this way:**

`http://[Your-Project-Name].imrapid.io/[The-Web-Page Name]`

For example:
`http://expert-bluewhale-loli.imrapid.io/index`

###Files
Using this tool you can upload any file you want to our servers and `GET` it later. 

###Backend Actions

By clicking on 'Backend Actions' you will be able to create a backend action, for example: Sign_up backend action (Endpoint). 

Give it a name that will describe it the best and go edit it. To create your endpoint use the 'Edit' button right after you're creating it, this will take you forward to the Endpoints (Backend Actions) Editor page =>

##Endpoints Editor
![](http://i.giphy.com/3oCWtzVbAwEzBnmF68.gif)

The editor is the core of our platform, using this tool you will be able to create any logic tree based any API we support. 

The editor is divided into the tools you need to create the endpoints:

###Blocks
APIs divided into backend actions -> Blocks = Drag and Drop them to open them.

###Code Snippet 
An `HTTP Access` code generator for iOS, Android and WEB.

###RUN Tool
The RUN tool, a.k.a the Action Panel is your tool to check the endpoint. It means that you will be able to find out 

Sometimes, it's good to check your endpoint with [**Postman**](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop?hl=en) also.

###Body Parameters

To use the #body parameters you should fill the 





#Calculate
![](http://i.giphy.com/26haHhYc5OPa8XKpi.gif)

##Calculate.add

**Use Case:** You are using leaderboard in your game and you want to add the number of user’s points after the game has ended.

**Parameters information:** 

Parameter | Use | Description
--------- | ------- | -----------
Num1 | Number of #body parameter | Will be the first number to be part of the function | 
Num2 | Number of #body parameter | Will be the second number to be part of the function
Sum | Object | Give your object a name, so you can print it later with the result.

**Returns Examples:** You will get the addition result. Something like 3+1=4? 

**How to test?** Use the 'RUN' tool [(How to?)](#)

<aside class="warning">Error - Use the response.SendMessage block to get an error message back.</aside>

<aside class="success">
Success — Use the response.SendMessage block to get a success message back. In the message field, use the #[Name of the object] to get it.
</aside>

##Calculate.substract

**Use Case:** Substract two numbers and get a resault.

**Parameters information:** 

Parameter | Use | Description
--------- | ------- | -----------
Num1 | Number of #body parameter | Will be the first number to be part of the function | 
Num2 | Number of #body parameter | Will be the second number to be part of the function
difference | Object | Give your object a name, so you can print it later with the result.

**Returns Examples:** You will get the substraction result. Something like 3-1=2? 

**How to test?** Use the 'RUN' tool [(How to?)](#)

<aside class="warning">Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
Success — Use the **response.SendMessage** block to get a success message back. In the message field, use the #[Name of the object] to get it.
</aside>

##Calculate.multiply

**Use Case:** Multiply two numbers and get a resault.

**Parameters information:** 

Parameter | Use | Description
--------- | ------- | -----------
Num1 | Number of #body parameter [(How to?)](##body-parameters) | Will be the first number to be part of the function | 
Num2 | Number of #body parameter [(How to?)](##body-parameters) | Will be the second number to be part of the function
Product | Object | Give your object a name, so you can print it later with the result.

**Returns Examples:** You will get the substraction result. Something like 3-1=2? 

**How to test?** Use the 'RUN' tool [(How to?)](#run-tool)

<aside class="warning">Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
Success — Use the **response.SendMessage** block to get a success message back. In the message field, use the #[Name of the object] to get it.
</aside>

##Calculate.random

**Use Case:** Print a random number between min and max limit.

**Parameters information:** 

Parameter | Use | Description
--------- | ------- | -----------
Max | Number of #body parameter [(How to?)](##body-parameters) | Will be the minimum number presented | 
Min | Number of #body parameter [(How to?)](##body-parameters) | Will be the maximum number presented
to | Object | Give your object a name, so you can print it later with the result.

**Returns Examples:** You will get a random number between the minimum and the maximum number.

**How to test?** Use the 'RUN' tool [(How to?)](#run-tool)

<aside class="warning">Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
Success — Use the **response.SendMessage** block to get a success message back. In the message field, use the #[Name of the object] to get it.
</aside>

##Calculate.divide

**Use Case:** Divide two numbers and get a resault.

**Parameters information:** 

Parameter | Use | Description
--------- | ------- | -----------
Num1 | Number of #body parameter [(How to?)](#body-parameters) | Will be the first number to be part of the function | 
Num2 | Number of #body parameter [(How to?)](#body-parameters) | Will be the second number to be part of the function
to | Object | Give your object a name, so you can print it later with the result.

**Returns Examples:** A result of two divided numbers. 3/3 = 1. 

**How to test?** Use the 'RUN' tool [(How to?)](#run-tool)

<aside class="warning">Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
Success — Use the **response.SendMessage** block to get a success message back. In the message field, use the #[Name of the object] to get it.
</aside>

#Database
The database is soo sooooo important!; Right now the database section is placed right after the Endpoints page in the platform. Go there to understand how does it works. 
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

#Google Places
##Places.getNearbyPlaces

**Name of the backend functions:** Get places near by; based on longitude, latitude and radius.

**How to use:** Go to [LatLong Generator](http://www.latlong.net/convert-address-to-lat-long.html) and get the latitued and longtitude of the point place you want to track.

**Use Case:** You want to show a user which places are near his location.

**Parameters information:** 

Parameter | Use | Description
--------- | ------- | -----------
latitude | For example: 32.075001| Use generater or Google Maps to get lat | 
longitude | For example: 34.783453 | Use generater or Google Maps to get long
radius | Use numbers | In meters. For example: 50 meters.
to | object | where do you want to save the file? Give it a name. For example: places

<aside class="warning">
For Example:
Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
For Example: 
- Use response.sendMessage block, 
- Message = Use the object you have used in the 'to' field to print the result. In this case we used #places
- Status = 200 (Success).
</aside>

#Stripe (Payment)
##Stripe.charge 

**The Endpoint Must Be in a `GET` method:** To add a stripe charge function => endpoint, go to the endpoint page and create new endpoint, while creating, click on 'advanced settings' and change the endpoint type to a `GET` type.

**Name of the backend functions:** Charge trough Stripe.

**Use Case:** Sell items trough your website, charge using stripe.

**Parameters information:** 

Parameter | Use | Description
--------- | ------- | -----------
amount | The amout of $ you want to charge| use numbers | 
currency | Use the currency you want to charge | for example USD
description | Description that will be sent to users | What is he paying for? Will be presented to the user
secretId | your secret ID | Go the [Stripe developers framework](https://dashboard.stripe.com/login) to get your secret ID
source | where the payment coming from | use the account you will place the charging on

<aside class="warning">
For Example:
Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
For Example: 
- Use response.sendMessage block, 
- Message = Use the object you have used in the 'to' field to print the result. In this case we used #places
- Status = 200 (Success).
</aside>

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
