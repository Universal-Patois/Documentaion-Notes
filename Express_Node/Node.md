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
# <r>Node.js</r>
## <o>What is Node.js?</o>

* A JavaScript runtime built on Chrome's V8 JavaScript engine.
* Single-threaded event-driven execution environment
## <o>What does Node.js do?</o>

* <h>Error first callbacks</h>- the first argument to a callback is always an error object

## <o>What does Node.js NOT do?</o>

* Handle specific requests for HTTPS verbs (GET, POST, SET, etc.)
* Separately handle specific requests for URL paths (routes)
* Serve static files
* Use templates to  dynamically generate responses

You can either write the code yourself or use Express to do all of these things.

### <y>Simple example of a Node.js server</y>

```javascript
// Load HTTP module
const http = require("http");

const hostname = "127.0.0.1";
const port = 8000;

// Create HTTP server
const server = http.createServer(function (req, res) {
  // Set the response HTTP header with HTTP status and Content type
  res.writeHead(200, { "Content-Type": "text/plain" });

  // Send the response body "Hello World"
  res.end("Hello World\n");
});

// Prints a log once the server starts listening
server.listen(port, hostname, function () {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

* If a dependency is only used during development, you should instead save it as a "development dependency" (so that your package users don't have to install it in production).
  * Ex: ```npm install eslint --save-dev```

## <o>Terminology</o>

* <h>**Route**</h> - A route is a combination of an HTTP verb(GET, POST, PUT, DELETE) and a URL path (endpoint), and a function that is called to handle that path.
  * <hh>*ex.*</hh> ```app.get('/things', function(req, res) { ... })```
* <h>**Controller**</h> - A controller is a function that is called when a route is matched. It is responsible for sending a response to the client.
  * <hh>*ex.*</hh> ```function(req, res) { ... }```
* <h>**Models**</h> - Models are objects that represent data in your application. They are usually constructed from data that is stored in a database.
  * <hh>*ex.*</hh> ```const thing = new Thing({ name: 'foo', description: 'bar' })```
* <h>**View**</h> - A view is a template that is used to render a response. It is usually a template that is populated with data from a model.
* <h>**Field**</h> - A field is a property of a model. It is usually a column in a database table.
* <h>**Schema**</h> - A schema is a definition of the fields that a model has. It is usually used to validate data before it is saved to the database.
  