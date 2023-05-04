<style>
r { color: Crimson }
o { color: Coral }
y { color: Khaki }
g { color: MediumSpringGreen }
b { color: SkyBlue }
i { color: Violet }
h { color:  Plum }
hh { color: Pink }
</style>
# [Express Notes](https://expressjs.com/)

## <o>Table of Contents</o>
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
* [Using a Database with Mongoose](#using-a-database)
* [Routes and Controllers](#routes-and-controllers)
* [Using a Template Engine](#template-primer)


## <h2 id="what-is-express"><o>What is Express?</o></h2>

* Express is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications.
* Unopinionated: You can insert almost any compatible middleware you like into the request handling chain, in almost any order you like.

## <h2 id="what-does-express-do"><o>What does Express do?</o></h2>

* Write handlers for requests with different HTTP verbs at different URL paths (routes)
* Integrate with "view" rendering engines in order to generate responses by inserting data into templates
* Set common web application settings like the port to use for connecting, and the location of templates that are used for rendering the response
* Add additional request processing "middleware" at any point within the request handling pipeline
* Express provides methods to specify what function is called for a particular HTTP verb (GET, POST, SET, etc.) and URL path (route) combination.

[back to top](#express-notes)

### <h2 id="simple-example-of-an-express-server"><y>Simple example of an Express server</y></h2>

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
## <h2 id="what-is-a-middleware"><o>What is a middleware?</o></h2>

* Middleware is a function that has access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. The next middleware function is commonly denoted by a variable named next.
* Middleware functions can perform the following tasks:
  * Execute any code.
  * Make changes to the request and the response objects.
  * End the request-response cycle.
  * Call the next middleware function in the stack.
* [Middleware Packages](https://expressjs.com/en/resources/middleware.html)

* **Middleware and routing functions are called in the order they are declared.**

* **For some middleware, it is important to know the order in which they are called.**
  
  <h>*For example: If session middleware depends on cookie middleware, then the cookie handler must be added first.*</h>

The <hh>**only**</hh> difference between a middleware function and a route handler callback is that middleware functions have a third argument ``next``, which middleware functions are expected to call if they are not that which completes the request cycle

[back to top](#express-notes)
## <h2 id="working-with-express"><o>Working with Express</o></h2>

### <h2 id="importing-modules"><y>Importing modules</y></h2>

* Importing modules is done with the ```require()``` function.
* Specify the name of the module to import as a string ```require('express')```
* You can create your own modules and import them as well
* If you want to export a complete object from a module, you can use ```module.exports```

<hh> You can think of ```exports``` as a shortcut to ```module.exports``` </hh>

### <h2 id="handling-errors"><y>Handling errors</y></h2>

* Express provides a built-in error handler that prints stack traces to the console.
* The middleware function takes in 4 arguments: ```err```, ```req```, ```res```, and ```next```
* The error handler is added as the last middleware function in the application.

<h>Note</h>: HTTP(404) and other errors are not treated as errors. You need to add a middleware function to handle them.

### <h2 id="using-databases"><y>Using databases</y></h2>

* Express app can use any database mechanism that is supported by Node.js.
  * MySQL, MongoDB, PostgreSQL, SQLite, Redis, etc.
* To use these you have to first install the database driver  using ```npm```
  * ```npm install mysql```
* In the Express app, you require the database driver, connect to the database, and then create, read, update, and delete (CRUD) operations.

<h>**Example:**</h> *Find 'mammal' records using MongoDB*

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
Another approach is the access the database indirectly, via an <h>**ORM (Object Relational Mapper)**</h>

* In this approach you define your data as "objects" and then use the ORM to map these objects to the underlying database format.
* The benefit of this approach is that you can think in terms of JavaScript objects rather than database semantics.

[back to top](#express-notes)
### <y>Rendering data (views)</y>

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

### <y>File structure</y>

* Typically it makes sense to split your application into files based on: 
  * Function:
    * Account management, blogs, discussion forums, etc.
  * Architectural problem domain:
    * Models, views, controllers, etc.

[back to top](#express-notes)

## <o>Setting up an Express application</o>

### <y>Installing Express Application Generator</y>

* A tool that generates an Express application "skeleton"

```npm install express-generator -g```

### <y>To create and Express app</y>

* Navigate to where you want to create it and run

```express (app name)```

<h>**OR**</h>

```npx express-generator (app name)```

<hh>*Then*</hh>

```javascript
  cd (app name)
  npm install
```

### <y>To run the app</y>

```DEBUG={app name}:* npm start```


### <y>Setting up server to restart on file changes</y>

```npm install --save-dev nodemon```

[More info](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/skeleton_website)
[Nodemon](https://www.npmjs.com/package/nodemon)

[back to top](#express-notes)

## <o>Using a database</o>

### <y>Designing the models needed for the app</y>

* The models are the objects that will be stored in the database.
* The model represents a collection of documents in the database that you can search.
  * The model's <hh>**instances**</hh> represent individual documents that you can save and retrieve.
* When designing the models it makes sense to have separate models for every object. 
  * (e.g. User, Blog, Comment, Genre, Category, etc.)
  * We want to be able to sort information based these models.
* <h>**Fields**</h> are the properties of the model.
  * (e.g. User: name, email, password, etc.)
* Models are defined using the ```Schema``` interface.
  * The ```Schema``` interface is used to define the fields of the model.

#### <g>UML (Unified Modeling Language) association diagram</g>

* A diagram that shows the relationships between the models and their multiplicities.
* <h>**Multiplicities**</h> are the number of instances of a model that can be associated with another model.
  * (e.g. A user can have many blogs, but a blog can only have one user.)

![Express Modeling Diagram Example](../Assests/library_website_-_mongoose_express.png)

#### <g>Schemas</g>

* A schema can have an arbitrary number of fields.
* Each one represents a field in the documents stored in MongoDB. 

* [**Scheme types (fields)**](https://mongoosejs.com/docs/schematypes.html)
```javascript
  const schema = new Schema({
    name: String,
    binary: Buffer,
    living: Boolean,
    updated: { type: Date, default: Date.now() },
    age: { type: Number, min: 18, max: 65, required: true },
    mixed: Schema.Types.Mixed,
    _someId: Schema.Types.ObjectId,
    array: [],
    ofString: [String], // You can also have an array of each of the other types too.
    nested: { stuff: { type: String, lowercase: true, trim: true } },
  });
```

* **Defining a Schema(and Creating a Model)**
```javascript
    // Require Mongoose
  const mongoose = require("mongoose");

  // Define a schema
  const Schema = mongoose.Schema;

  const SomeModelSchema = new Schema({
    a_string: String,
    a_date: Date,
  });

  // Compile model from schema
  const SomeModel = mongoose.model("SomeModel", SomeModelSchema);
```

* [**Validation**](https://mongoosejs.com/docs/validation.html) allows you to specify acceptable range of values and error message for validation failures


### <y>Setting up the database</y>

* We will use the [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) cloud service to host our database.
  * The MongoDB server can be downloaded and installed locally as well.
* We will use Mongoose to connect to MongoDB for this example.
  * ```npm i mongoose```

* Mongoose requires a connection to MongoDB database

#### <g>To connect to a  locally hosted MongoDB database</g>

```javascript
// Import the mongoose module
const mongoose = require("mongoose");

// Set `strictQuery: false` to globally opt into filtering by properties that aren't in the schema
// Included because it removes preparatory warnings for Mongoose 7.
// See: https://mongoosejs.com/docs/migrating_to_6.html#strictquery-is-removed-and-replaced-by-strict
mongoose.set('strictQuery', false);

// Define the database URL to connect to.
const mongoDB = "mongodb://127.0.0.1/my_database";

// Wait for database to connect, logging an error if there is a problem 
main().catch(err => console.log(err));
async function main() {
  await mongoose.connect(mongoDB);
}
```

[back to top](#express-notes)

## <h2 id="routes-and-controllers"><o>Routes and Controllers</o></h2>

### <y>Route Functions</y>

* A route function is a function that is called when a route is matched.
``` javascript
  router.get("/about", function (req, res) {
  res.send("About this wiki");
});
```
* The about route is defined using the ```router.get()``` method.
* It responds only to HTTP GET requests.
* The first argument is the route path(URL path).
* The second argument is  a callback function that will be invoked if an HTTP GET request with the path is recieved.
  * The callback function takes three arguments:
    * ```req``` - The HTTP request object
    * ```res``` - The HTTP response object
    * ```next``` - The next middleware function in the application's request-response cycle.
* There are many different response methods that can be used to send data to the client.
  * ```res.send()``` - Sends a response of any type.
  * ```res.json()``` - Sends a JSON response.
  * ```res.render()``` - Renders a view template.
  * ```res.redirect()``` - Redirects a request.
  * ```res.sendFile()``` - Sends a file as an octet stream.
  * ```res.download()``` - Sends a file as an attachment.
  * ```res.sendStatus()``` - Sets the response status code and sends its string representation as the response body.

### <y>Route Paths</y>

* Route paths define the endpoints at which requests can be made.
* Route paths can be strings, string patterns, or regular expressions.

#### <g>Route path: string pattern syntax</g>

* ```?``` - Matches the preceding character 0 or 1 time. The endpoit must have 0 or 1 of the preceding character(or group).
  * ```/ab?cd``` - Matches endpoints```/acd``` or ```/abcd```
* ```+``` - Matches the preceding character 1 or more times. The endpoint must have 1 or more of the preceding character(or group).
  * ```/ab+cd``` - Matches endpoints ```/abcd```, ```/abbcd```, ```/abbbcd```, etc.
* ```*``` - The endpoint may have an arbitrary string where the ```*``` character is placed.
  * ```/ab*cd``` - will match endpoints ```/acd```, ```/abXcd```, ```/abbcd```, ```/abSOMErandomTEXTcd```, etc.
* ```()``` - Groups subpatterns into a larger pattern. The endpoint must match the entire group. Grouping match on a set of characters to perform another operation on
  * ```/ab(cd)?e``` - will perform a ```?```-match on the group ```(cd)```- it will match ```/abe``` and ```/abcde```

#### <g>Route path: regular expressions</g>

* Route paths can also be JavaScript regular expressions.

``` javascript
  app.get(/.*fish$/, function (req, res) {
  // …
});
```

* The above route will match any endpoint that ends with the word ```fish```.
  * *ex.* ```/goldfish``` and ```/catfish```, but not ```/goldfishes``` or ```/catflap```

#### <g>Route Parameters</g>

* Route parameters are named URL segments that are used to capture the values specified at their position in the URL.
* The named segments are prefixed with a colon ```:``` and then the name.
  * <h>*ex.*</h> ```/user/:userId/book/:bookId```
* The names of route parameters must be made up of "word characters" ```[A-Z, a-z, 0-9, and _]```.

``` javascript
  app.get("/users/:userId/books/:bookId", function (req, res) {
  // Access userId via: req.params.userId
  // Access bookId via: req.params.bookId
  res.send(req.params);
});
```

#### <g> Handling Errors in the Route Functions</g>

* ``next`` - Is a third parameter that called with the route functions.
  * It can be used to pass errors to the Express middleware chain.
  * <h>*ex.*</h>
  ``` javascript
    router.get("/about", (req, res, next) => {
    About.find({}).exec((err, queryResults) => {
      if (err) {
        return next(err);
      }
      //Successful, so render
      res.render("about_view", { title: "About", list: queryResults });
    });
    });
    ```
  * The framework is designed for use with asynchronous functions that take a callback function
  * That's a problem because making Mongoose database queries that use Promise-based APIs
  * Which may throw exceptions in our route functions (rather than returning errors in a callback)


* The solution is to wrap the route function in a ```try/catch``` block
  * <h>*ex.*</h>
``` javascript
// Import the module
const asyncHandler = require('express-async-handler')

exports.get("/about", asyncHandler(async (req, res, next) => {
  const successfulResult = await About.find({}).exec();
  res.render("about_view", { title: "About", list: successfulResult });
}));
```
  * The ```asyncHandler``` function is a wrapper that will catch any errors thrown by the route function and pass them to ```next()```
  * This prevents having to add ```try/catch``` blocks to every route function.
``` javascript
  exports.get("/about", function (req, res, next) {
  try {
    const successfulResult = await About.find({}).exec();
    res.render("about_view", { title: "About", list: successfulResult });
  }
  catch (error) {
    return next(error);
  }
};
```

[Back to top](#express-notes)

## <h2 id="template-primer"><o>Template Primer</o></h2>

* A template is a text file defining the structure or layout of an output file, with placeholders used to represent where data will be inserted when the template is rendered.
* In Express, templates are referred to as views.

### <y>Example Template File</y>

* The following is an example of a template file that uses the Pug template engine.
* Indentation is used to define nested elements
* If a tag is followed by the equals sign, the following text is treated as a JavaScript expression (either defined in the file or passed into the template from Express).
  * ```h1 ``` tag will be variable ```title```
* If there is no equals symbol after the tag then the content is treated as plain text.
* You can insert escaped and unescaped data using the ```#{}``` and !```{}``` syntax respectively.
* You can use the pipe ```('|')``` character at the beginning of a line to indicate "plain text".
* Pug allows you to perform conditional operations using ```if```, ```else```, ```else if``` and ```unless```.
* You can also perform loop/iteration operations using ```each-in``` or ```while``` syntax.

``` html
doctype html
html(lang="en")
  head
    title= title
    script(type='text/javascript').
  body
    h1= title

    p This is a line with #[em some emphasis] and #[strong strong text] markup.
    p This line has un-escaped data: !{'<em> is emphasized</em>'} and escaped data: #{'<em> is not emphasized</em>'}.
      | This line follows on.
    p= 'Evaluated and <em>escaped expression</em>:' + title

    <!-- You can add HTML comments directly -->
    // You can add single line JavaScript comments and they are generated to HTML comments
    //- Introducing a single line JavaScript comment with "//-" ensures the comment isn't rendered to HTML

    p A line with a link
      a(href='/catalog/authors') Some link text
      |  and some extra text.

    #container.col
      if title
        p A variable named "title" exists.
      else
        p A variable named "title" does not exist.
      p.
        Pug is a terse and simple template language with a
        strong focus on performance and powerful features.

    h2 Generate a list

    ul
      each val in [1, 2, 3, 4, 5]
        li= val
```

The values of all attributes are escaped (e.g. characters like ">" are converted to their HTML code equivalents like "&gt;") to prevent JavaScript injection or cross-site scripting attacks.

