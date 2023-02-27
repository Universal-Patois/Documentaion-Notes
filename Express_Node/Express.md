# [Express Notes](https://expressjs.com/)

## What is Express?

* Express is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications.
* Unopinionated: You can insert almost any compatible middleware you like into the request handling chain, in almost any order you like.

## What does Express do?

* Write handlers for requests with different HTTP verbs at different URL paths (routes)
* Integrate with "view" rendering engines in order to generate responses by inserting data into templates
* Set common web application settings like the port to use for connecting, and the location of templates that are used for rendering the response
* Add additional request processing "middleware" at any point within the request handling pipeline
* Express provides methods to specify what function is called for a particular HTTP verb (GET, POST, SET, etc.) and URL path (route) combination.

## What is a middleware?

* Middleware is a function that has access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. The next middleware function is commonly denoted by a variable named next.
* Middleware functions can perform the following tasks:
  * Execute any code.
  * Make changes to the request and the response objects.
  * End the request-response cycle.
  * Call the next middleware function in the stack.
* [Middleware Packages](https://expressjs.com/en/resources/middleware.html)