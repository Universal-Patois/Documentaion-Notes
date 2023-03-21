# Node.js
## What is Node.js?

* A JavaScript runtime built on Chrome's V8 JavaScript engine.
* Single-threaded event-driven execution environment
## What does Node.js do?

* error first callbacks- the first argument to a callback is always an error object

## What does Node.js NOT do?

* Handle specific requests for HTTPS verbs (GET, POST, SET, etc.)
* Separately handle specific requests for URL paths (routes)
* Serve static files
* Use templates to  dynamically generate responses

You can either write the code yourself or use Express to do all of these things.

### Simple example of a Node.js server

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


  