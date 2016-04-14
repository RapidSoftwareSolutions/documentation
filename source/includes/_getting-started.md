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
