# [Express Notes](https://expressjs.com/)

**Contents:**
* [What is Express?](#what-is-express)
* [What does Express do?](#what-does-express-do)
* [Simple example of an Express server](#simple-example-of-an-express-server)
* [What is a middleware?](#what-is-a-middleware)
* [Working with Express](#working-with-express)
* [Importing modules](#importing-modules)
* [Handling errors](#handling-errors)
* [Using databases](#using-databases)
* [Rendering Data](#rendering-data)
* [File Structure](#file-structure)


## What is Express?

* Express is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications.
* Unopinionated: You can insert almost any compatible middleware you like into the request handling chain, in almost any order you like.

## What does Express do?

* Write handlers for requests with different HTTP verbs at different URL paths (routes)
* Integrate with "view" rendering engines in order to generate responses by inserting data into templates
* Set common web application settings like the port to use for connecting, and the location of templates that are used for rendering the response
* Add additional request processing "middleware" at any point within the request handling pipeline
* Express provides methods to specify what function is called for a particular HTTP verb (GET, POST, SET, etc.) and URL path (route) combination.

[back to top](#express-notes)

### Simple example of an Express server

```javascript
// Import express
const express = require("express");
// Object traditionally named app. Has methods for routing HTTP requests, configuring middleware, rendering HTML views, etc.
const port = 3000;

// Shows a route definition (```GET``` request to the root path)
// The app.get() method specifies a callback function that is invoked whenever there is a HTTP ```GET``` request to the root path (```/```) of the server.// 
// The callback function takes a request and response object as arguments and calls ```send()``` on the response object to return the string "Hello World!".
app.get("/", function (req, res) {
  // Route handler (callback function) (can use other methods like ```res.json()```, ```res.sendFile()```, etc.)
  res.send("Hello World!");
});

// Starts the server and prints a log comment to the console.
app.listen(port, function () {
  console.log(`Example app listening on port ${port}!`);
});
```
## What is a middleware?

* Middleware is a function that has access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. The next middleware function is commonly denoted by a variable named next.
* Middleware functions can perform the following tasks:
  * Execute any code.
  * Make changes to the request and the response objects.
  * End the request-response cycle.
  * Call the next middleware function in the stack.
* [Middleware Packages](https://expressjs.com/en/resources/middleware.html)

* **Middleware and routing functions are called in the order they are declared.**

* **For some middleware, it is important to know the order in which they are called.**
  
  *For example: If session middleware depends on cookie middleware, then the cookie handler must be added first.*

The **only** difference between a middleware function and a route handler callback is that middleware functions have a third argument ``next``, which middleware functions are expected to call if they are not that which completes the request cycle

[back to top](#express-notes)
## Working with Express

### Importing modules

* Importing modules is done with the ```require()``` function.
* Specify the name of the module to import as a string ```require('express')```
* You can create your own modules and import them as well
* If you want to export a complete object from a module, you can use ```module.exports```

*** You can think of ```exports``` as a shortcut to ```module.exports``` ***

### Handling errors

* Express provides a built-in error handler that prints stack traces to the console.
* The middleware function takes in 4 arguments: ```err```, ```req```, ```res```, and ```next```
* The error handler is added as the last middleware function in the application.

Note: HTTP(404) and other errors are not treated as errors. You need to add a middleware function to handle them.

### Using databases

* Express app can use any database mechanism that is supported by Node.js.
  * MySQL, MongoDB, PostgreSQL, SQLite, Redis, etc.
* To use these you have to first install the database driver  using ```npm```
  * ```npm install mysql```
* In the Express app, you require the database driver, connect to the database, and then create, read, update, and delete (CRUD) operations.

**Example:** *(Find 'mammal' records using MongoDB)*

```javascript
const MongoClient = require("mongodb").MongoClient;

MongoClient.connect("mongodb://localhost:27017/animals", (err, client) => {
  if (err) throw err;

  const db = client.db("animals");
  db.collection("mammals")
    .find()
    .toArray((err, result) => {
      if (err) throw err;
      console.log(result);
      client.close();
    });
});
```
Another approach is the access the database indirectly, via an **ORM (Object Relational Mapper)**

* In this approach you define your data as "objects" and then use the ORM to map these objects to the underlying database format.
* The benefit of this approach is that you can think in terms of JavaScript objects rather than database semantics.

[back to top](#express-notes)
### Rendering data (views)

* Express provides a built-in view engine for rendering HTML views.
* Template engines (view engines) allow you to specify the structure of your output document in a template
* Placeholders in the template are replaced when a page is generated.
* Express supports the following template engines:
  * [Pug](https://pugjs.org/api/getting-started.html)
  * [EJS](https://ejs.co/)
  * [Handlebars](https://handlebarsjs.com/)
  * [Mustache](https://mustache.github.io/)
  * [Dust](http://www.dustjs.com/)
  * [Nunjucks](https://mozilla.github.io/nunjucks/)
  * [Twig](https://twig.symfony.com/)
  * [Liquid](https://shopify.github.io/liquid/)

Templates are often used to create the HTML for web pages, but they can also be used to generate other types of documents.

### File structure

* Typically it makes sense to split your application into files based on: 
  * Function:
    * Account management, blogs, discussion forums, etc.
  * Architectural problem domain:
    * Models, views, controllers, etc.

[back to top](#express-notes)

## Setting up an Express application

### Installing Express Application Generator

* A tool that generates an Express application "skeleton"

```npm install express-generator -g```

### To create and Express app

* Navigate to where you want to create it and run

```express (app name)```

**OR**

```npx express-generator (app name)```

*Then*

```javascript
  cd (app name)
  npm install
```

### To run the app

```DEBUG=helloworld:* npm start```