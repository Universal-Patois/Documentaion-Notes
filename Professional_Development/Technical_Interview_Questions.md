<style>
r { color: Crimson }
o { color: Coral }
y { color: Khaki }
g { color: MediumSpringGreen }
b { color: SkyBlue }
i { color: Violet }
h { color:  Plum }
hh { color: Pink }
l { color: Lemonchiffon}
</style>

# <h1 id="top">Technical Interview Questions</h1>

## Tell me two advantages of testing your code.
- [x] notecard
* Forces you to look at the problem at a high level
* Forces you to write modular code / SRP
* Provides future integrity for your code
* Provides a blueprint for those learning your codebase
* Computers are faster and more accurate at testing. 


## What factors influence whether you’ll take a progressive enhancement vs. graceful degradation approach to building an application?
- [x] notecard
* Audience! Does the site need to emphasize accessibility or features.
* Progressive Enhancement will start out very basic and can add features, best for accessibility. (Medicare Enrollment or similar)
* Graceful Degradation will have more fancy features and scales back. (Video game platform?)

## Define the term ‘MVC’ and explain how an application is architected when following MVC patterns.
- [x] notecard
* Model, View, Controller - seperates data and presentation layers
* Model: data structure
* View: Represents information...chart, diagram, table...reusable
* Controller: takes user input and converts it to commands for the model or view

## What does CORS stand for and what issue does it address?
- [x] notecard
* Cross Origin Resource Sharing - it gives an application running at one origin access to selected resources from a different origin

## In as much detail as possible, describe the request-response cycle.
- [x] notecard
* Foundation of any data exchange on the web
* Client-server protocol....client requests and the server responds
1) A user types a url in their browser and hits enter
2) The browser takes the address and builds an HTTP Request addressed ot the server at the given url
3) The request is sent to the ISP and then sent through the internet to the server
4) The server reads the request
5) The server generates a HTTP Response
6) The response is sent through the internet back to your computer
7) The browser reads the response and if successful will display the content.

## Tell me 3 new features of CSS3.
- [x] notecard
* Border-radius to round corners
* Drop-shadows
* Gradients: linear, radial, repeating...
* Media queries


## What’s the difference between display: inline and display: inline-block?
- [x] notecard
* Display inline-block allows for width and height style attributes as well. Inline-block also respects the top/bottom margins/paddings, inline does not.

## What is a pseudo class? What are they used for?
- [x] notecard
* A key word added to a selector that specifies a special state of the selected element(s). :hover, :active, :enabled, :visited...

## Describe z-index and how stacking context is formed.
- [x] notecard
* Sets the z-order of a positioned element and its descendants or flex items. Overlapping elements with a larger z-index cover those with a smaller one. Keyword=positioned!




## Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
- [x] notecard
* Hard to keep track of global variables
* Anyone can update a global variable, they have no closure
* Bad smell, lazy
* Name clashes with global variables
* Maybe get into issues with changing the window or document (?)

## What does event bubbling or event propagation mean?
- [x] notecard
* Event Propagation: roughly the order in which different DOM elements are notified of an event
* Can be used for dynamic elements, elements that were added to the page after the initial load...can't add event listeners to them
1) Event Capturing - listeners are fired from the top of the DOM tree down
2) Event Targeting - listeners are fired on the source of the event
3) Event Bubbling - listeners are fired from the target of the event up
* Event Bubbling is what we use to handle the events
Use:
* Put a single handler on a container
* In the handler, check the source of the event using event.target
* If the vent happens inside an element that interests you...handle the event

## What’s the difference between undefined and null
- [x] notecard
* Null is the intentional absence of a value...
* Undefined is a variable that has been declared but not assigned a value


## What is Ajax?
- [x] notecard
* Asynchronous JavaScript and XML...nowadays JSON is used more than XML...JSON is lighter and par of JavaScript
* fetch!

## What is "use strict";? What are the advantages and disadvantages to using it?
- [x] notecard
* Introduced in ECMAScript 5 (2009). Opts out of sloppy mode. Strict and non-strict can coexist. 
** Eliminates some JavaScript silent errors by changing them to throw errors.
** Fixes mistakes that make it difficult for JavaScript engines to perform optimizations: strict mode can sometimes be made to run faster than identical code that is not in strict mode.
** Prohibits some syntax likely to be defined in future versions of JavaScript


## What are the pros and cons of using Promises instead of callbacks?
- [x] notecard
* Promises are cleaner and more organized...no callback hell with multiple asynchronous operations at a time, promises can chain .thens
* Promises have better error handling
* Promise.all can be used to batch async operations, receive all as one array 
* Promises are built over callbacks

* Callbacks are a bit simpler and can have slightly better performance
* Have to know how to handle a Promise, not just an object

## What is a closure, and how/why would you use one?
- [x] notecard
* A closure is when an inner function has access to the outer functions variables and can remember the environment in which it was created. The outer functions variables are protected by the closure and can only be manipulated by code defined within that function.
* Can be used to protect variables from outside manipulation (could still change if really tried)
* Steps: 
    1) Define a function within a function
    2) Return the inner function at end of outer function (back that takes the lexical scope with it) NOTE: return the function definition, don't invoke it displayName not displayName()
        Lexical scope - next scope out, what wraps around a function (aka static scope)
    3) Save the return function in a variable to capture it
    4) Call teh function that has been created in a different scope

    function greet() {
        let name = 'Alan'
        function displayName() {
            console.log(name)           (step 1)
        }
        return displayName              (step 2)
    }

    var createGreeting = greet()        (step 3)
    createGreeting() // 'Alan'          (step 4)
    
## What advantages does React offer? What about disadvantages?
- [x] notecard
* Virtual DOM increases performance, only updates what is needed, when needed
* JSX makes it easy to write JavaScript in HTML 
* Components are independent, standalone and can be reused...modular code structure
* Easy to store application data either with state, hooks or redux



## In an HTML file, what does the ‘doctype’ keyword do?
- [x] notecard
* Doctype ensures that the browser makes a best-effort attempt to follow the relevant specifications, rather than using a different rendering mode that is incompatible with some specifications.
* It is information to the browser about what document type to expect.

## Give an example of a self-closing HTML tag.
- [x] notecard
* <input />, <img />, <br />, <meta />

## What’s the difference between window.onload and onDocumentReady
- [x] notecard
* window.onload will execute when the browser has loaded the DOM tree and all other resource...images, objects, etc. (standard DOM event)
* onDocumentReady executes when the DOM tree is built, but does not wait for the other resources (specific to jQuery)

## Give an example of an element that is considered a ‘block-level’ element? An example of an inline element? What’s the difference between block-level and inline elements?
- [x] notecard
* Block level occupies the entire width of its container element. Nothing can sit next to it. Mean girl
* Block: <h1> - <h6>, <header>, <footer>, <nav> <form>, <ol>, <ul>, <li>

* Inline level only occupes the space bounded by the opening and closing tags. It does not break the flow of content
* Inline: <a>, <em>, <strong>, <img>, <input>, <label>, <select>

## What could we use instead of <b> tags for bold and <i> tags for italics to make our ## HTML more semantic?
- [x] notecard
* <strong> for bold 
* <em> for italics

## What is the purpose of article, section, header and footer tags? Please explain with an example and why we should not use divs.
- [x]
* It is more semantic. Div does not specify what it is being used for so it is hard for those with screen readers. It is better to use a more semantic tag instead of div with aria role. So <header> is much better than <div role="header">
<article> - used for a blog post, magazine article, news article, etc. Represents a self-contained composition in a document, page, application or site which is intende to be independently distributable or reusable.
<section> - represents a standalone section, whcih doesn't have a more speific semantic element to represent it. Typically they have a heading.
<header> - represents introductory content, typically a group of introductory or navigational aids. Logo, search form, nav bar, etc
<footer> - root element, at bottom of page, info on the autor, copyright data, links to other pages...about, careers, etc

## What are HTML data attributes?
- [x] notecard
* They allow us to store extra information on standard, semantic HTML elements without other hacks. Allows us to store extra information that doesn't have any visual representation. Can be used for jQuery to query it. 
* data-id, data-index-number, data-name
* datase-id, dataset-index-number, dataset-name
<!-- <article
    id="electric-cars"
    data-id="123" >...</article> -->
const article = document.querySelector('#electric-cars')
article.dataset.id => "123"

## What is the event loop?
- [x] notecard
* Describes async JavaScript
* JavaScript is single-threaded
* Callstack is FILO
* When an async function is run, it is sent off to the browser API and the callstack continue
* Once the aync function is resolved (returned?), the function is sent to the event queue (first in, first out)
* Event Queue constantly checks to see if callstack is clear..once clear, pushes queue to call stack
* Never blocking



## What is the concept of state in React?
- [x] notecard
* State holds data that represents the actual data of an application. 

## What is the virtual DOM in React?
- [x] notecard
* A copy of the dom that is compared to changes that just occured. If needed, it will update the real dom accordingly
* Enhances performance
* Detects state and props changes
* Compares  the new version to the previous version of the virtual dom
* Updates are sent to the real Dom for re-rendering the UI

## How is an array different from an object?
- [x] notecard
* An object gives key value pairs where the key can be customized...
* Arrays are objects but the keys are numbers, 0 - i

## What is the DOM? How is the virtual dom different?
- [x] notecard
* Document Object Model - programming interface for HTML and XML documents. It represents the page so that programs cna change the document structure, tsyle and content. It is an object-oriented representation of the web page which can be modified through languages like JavaScript
* Virtual DOM is a copy of the Dom that gets compared to previous copies in frameworks like React and Vue. THe actual DOM is updated only as needed based on the changes.

## What does npm eject do?
- [x] notecard
* Removes the single build dependency from your project. Use if you are not satisfied with the build tool and configuration choices.
* It will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) into your pojrect as dependencies in package.json.

## What does npm build do?
- [x] notecard
* Builds the app for production to the build folder. It correctly bundles (react) in production mode and optimizes the build for the best performance. The build is minified and the filenames include the hashes.

## How do you make sure your project meets the requirements you have received?
## What IDE do you use?
- [x] notecard
* Integration Development Environment
* VS Code - error handling with TypeScript, shortcuts, git 

## How does json work?
- [x] notecard
* JavaScript Object Notation is a standard text-based format for representing structured data based on JavaScript object syntax. It is commonly used for transmitting data in web applications. 
* Alternate to XML as a standard for sending information back and forth over the web. 
* Subset of JavaScripts' object syntax
* Objects are stringified before being sent and parsed upon being received

## What is a react component?
- [x] notecard
* Function or class
* Standalone, independents parts of an application that are responsible for handling a single UI element

## Whats the difference between map state to props and map dispatch to props?
## What problems does redux solve?
- [x] notecard
* Redux solves the problem of passing data around in larger applications. Without it you may have to pass data through mulitple components, which do not need access to the data, just to get it where you need it. Redux allows us to store all of our data in a central location and then provide acccess to only the components that need it.

## What are libraries you have used?
- [x] notecard
* jQuery, Chai, React Testing Library, React (framwork), Vue (framework)
## What are frameworks you have used?
- [x] notecard
* React, Vue, Express

## How are props different from state?
- [x] notecard
* Props is an object that is given from it's parent component down to the child component. Can hold variables and methods.
* State holds data that represents the actual state of an application. State can be changed and mutated through use interactions.

## Do you know the concept of SCRUM?
- [x] notecard
* A SCRUM is an agile framework for developing applications. It is based around small teams completing goals during a sprint, which is usually a couple of weeks long. Common stages include requirements, design, implementation, Q/A and customer delivery/feedback. Its benefits include: responsiveness to the user through user feedback, easier to change course, possible revenue generation at earlier staages. 

## What is JSX?
- [x] notecard
* A mix of JavaScript and XML that facilitates rendering the appropriate HTML components. It allows you to write HTML in your JavaScript and JavaScript in your HTML.

## How is JSX different from HTML?
- [x] notecard
* It allows JavaScript to be directly in the HTML including variables and methods. Some attributes are similar but differetnly named, class v className.

## Explain how a branch works
- [x] notecard
* A branch is a way to break off of the code and implement features, bug fixes, etc. It allows a user to add, modify and remove code without affecting the main/master branch. Useful for development as it allows you to make commits before a feature is fully implemented.


## Whats the difference between ES5 and ES6?
- [x] notecard
* arrow functions
* object destructuring
* spread operator
* Promise to resolve or reject a request
* Import & export modules


## How do you interact with APIs on the front end?
- [x] notecard
* Fetch, Promise.All, Axios
* Make CRUD requests

## Whats the difference between an HTTP request and response?
- [x] notecard
* The request is sent by the client asking the server for a resource. The server then replies with a response, which contains the resource (? points to the resource)

## What does a 200 status code mean?
- [x] notecard
* OK - the request has succeeded

## What does a 400 status code mean?
- [x] notecard
* Bad Request - the server cannot process the request because of a client side error

## What is chaining in javascript?
- [x] notecard
* Chaining methods together...
* numbers.split('').pop('').join('')
* fetch(url).then(res => res.json()).catch(err => console.error(err))

## How do you stay up-to-date on JS and React news/improvements?
- [x] notecard
* JavaScript weekly, Medium subscription, Twitter, 

## Why use cookies?
- [x] notecard
* They allow the browser to store basic datra which can improve the user experience. Can remember user name, login info, etc

## Have you used local storage?
* Yes!

## Whats the difference between let and const and var?
- [x] notecard
* let/const are part of ES2015
* Let/var will allow you to reassign a variable (primitive only) where const will not allow you to reassgin its value
* var, let, const can all be globally scoped
* var, let, const can all be functionally scoped
* let and const can be block scoped (var leaks!)
* let/const do not hoist...var does

## Whats your experience with React Hooks? Why use them?
- [x] notecard
* useState, useEffect...some useContext
* They allow us to write all of our components as functional components which are lighter and faster than class components
* Easier to write/update than state

## What method was you use to search an array and return a value?
- [x] notecard
* Can use find or filter to search an array

## How would you find all the values for a specific key in an array of objects?
- [x] notecard
* Iterate over the array and then while on a specific object, iterate again over the array that matches the key. An iterator nested inside an iterator.
* ? Iterate over the array of objects and check each one to see if it has the key...reduce the array of objects with a return value of an array of all the values matching the key.

## Why is it generally a good idea to position CSS <link>s between <head></head> and JS <script>s just before </body>? Do you know any exceptions?
- [x] notecard
* CSS files get applied regardless of if the DOM has rendered or not. It looks better because the style is there first...otherwise, if linked further down, a slow page load would show plain HTML before any styling loaded. CSS in the head is HTML standard. Other developers know to look for it there. 
* JavaScript is linked in the bottom because whenever a browser encounters any JS, it parses it and executes it on the spot. If it were at the top, it would make the page rendering slow. Also, since the DOM won't be fully rendered, JavaScript won't be able to manipulate the elements.

## Do you know what a bearer token is in terms of JWT?
- [ ] notecard
* JSON Web Token
* Access token, a cryptic string
* Used with the Twitter Developer API


## What are some popular NodeJS Modules?
- [ ] notecard
????
* http - includes classes, methods and events to create the http server
* url - includes methords for URL resolution and parsing
* querystring - includes methods to deal with query string
* path - methods to deal with file paths
* fs - classes, methods and events ot work with file I/O
* util - utility functions for programmers
* ?
* _dirname, _filename, exports,



## In as much detail as possible, explain how JSON Web Tokens work.
- [ ] notecard
* ? Uses asymmetric (public-key) cryptography instead of passwords or SMS texts for registering, authenticating and second-factor authentication for websites
* Access tokens
* Signed tokens using public/private keys, can verify the integrity of the claims contained with the token.
* Used for authorization and information exchange
* Once a user signs on their requests include the JWT allowing them access to certain routes, services, resources.
* Single Sign On uses JWT...cross domains
* Private or public keys

## Can you describe what responsive design is to you and how you would implement it?
- [ ] notecard
* Design that responds to the user's behavior and environment. Screen size, platform and orientation
* Media queries, 

## In as much detail as possible, explain how you would localize an application.
- [ ] notecard
? Like this: Localization is the adaptation of a product or service to meet the needs of a particular language, culture or desired population's "look-and-feel.
* Research the culture. Try to find out if there are certain colors, etc to avoid
* If you aren't fluent in the language, find someone who is to help translate the text
* Translate the site
* User test, user test, user test - make sure there is no cultural issues

## Name three strategies for fixing cross-browser inconsistencies.
- [ ] notecard
* In CSS, Internet Explorer conditional comments
* In CSS, use vendor prefixes
* Use a validation tool like the W3C Markup Validation Service (?)

## What are some tools and strategies you use to prevent shipping unstable code to production?
- [ ] notecard
* Test before each deployment!
* Continuous Integration - Travis CI linked to Heroku

## Get all Error codes

## What can you tell me about Rest APIs?

## Explain why the following doesn’t work as an IIFE: function foo(){ }();. What needs to be changed to properly make it an IIFE? Why?

## If you have two elements inside of an outer containing element, one with float: left; and the other with float: right, how can you ensure that the containing element expands around the floated elements and does not collapse?