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
  - getting-started
  - system-overview
  - p-facebook
  - p-database
  - p-delivery
  - p-files
  - p-stripe
  - p-calculate
  - p-googleplaces
  - p-ebay
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