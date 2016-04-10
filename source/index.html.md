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

Welcome to RapidAPI, the first platform allows you to build the backend for your app based on common APIs. Using a simple drag and drop edtior you will be able to create any logic to run your app and easily connect to any platform.

**How it's all started?**

We were at a Hackathon... And we've seen that all the teams were working on the same backend at the same time... So the first part of the Hackathon has gone to Installing servers, understanding APIs and creating logic. But, the interesting thing is that they all used the same APIs and same backends for their apps. We have created an amazing platform allows you to build a backend using drag and drop editor, with our platform you will be able to be to spend 10% of your time on backend development and to devote 90% of your time on Product, Design and Frontend development.

Cheers!

RapidAPI Team

# Overview Page 
The overview page will show you the following information:

- Number of Backend Actions (Endpoints), Numbers (For sending SMS messages), And Databases you've used in your project.
- Basic Tutorials.
- Collaborators - Here you can share your project with other teammates. 
- Your Latest Activity.
- Basic Statistics.

# Endpoints Page
The endpoints page is the core of your app. Through this page you can create the backend actions for your app, create static pages based on HTML, CSS and JS and upload files. 

![](http://i.giphy.com/l0LJdmkawpJ1lnzpK.gif)

##Web Pages

By clicking on Web Pages you will be able to create a static webpage that will be host on our servers. **The URL of the web page will be structured this way:**

`http://[Your-Project-Name].imrapid.io/[The-Web-Page Name]`

For example:
`http://expert-bluewhale-loli.imrapid.io/index`

##Files
Using this tool you can upload any file you want to our servers and `GET` it later. 

##Backend Actions

By clicking on 'Backend Actions' you will be able to create a backend action, for example: Sign_up backend action (Endpoint). 

Give it a name that will describe it the best and go edit it. To create your endpoint use the 'Edit' button right after you're creating it, this will take you forward to the Endpoints (Backend Actions) Editor page =>

#Endpoints Editor
![](http://i.giphy.com/3oCWtzVbAwEzBnmF68.gif)

The editor is the core of our platform, using this tool you will be able to create any logic tree based any API we support. 

The editor is divided into the tools you need to create the endpoints:

##Blocks
APIs divided into backend actions -> Blocks = Drag and Drop them to open them.

##Code Snippet 
An `HTTP Access` code generator for iOS, Android and WEB.

##RUN Tool
The RUN tool, a.k.a the Action Panel is your tool to check the endpoint. It means that you will be able to find out 

Sometimes, it's good to check your endpoint with [**Postman**](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop?hl=en) also.

##Body Parameters

To use the #body parameters you should fill the 





#Calculate Backend Fucntions
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
![](http://i.giphy.com/l3Ts3QZR8xVCdKi5y.gif)

#Send SMS

#Send Email
##delivery.sendPlainEmail

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
Success — Use the **response.SendMessage** block to get a success message back. In the message field, use the #[Name of the object] to get it.
</aside>


