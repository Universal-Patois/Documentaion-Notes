# Angular Notes

## Terminology

* ng: aNGular

### *Modules*

* Every Angular app has a root module named `App Module`
* A module is a collection of Angular components, directives, services, pipes, ect...
* They are sharable units with different types
  * system modules(Router)
  * custom modules
  * third party modules(ngrx, rxjs)
* These modules can be lazy-loaded. Meaning they only get loaded when they are needed. Improving performance
* Many modules make of an application

### *Components*

* Is the most basic building block of UI in an Angular app
* Controls a parch of screen called a view
* Display data on the screen, listen for user input, and take action on input
* Can use other components declared within the same module
* For components outside its module they need to be exported from that module and imported into the module that needs the functionality
* Should not fetch or save data directly - only focus on presenting data and delegate data access to a *service*

#### Angular components vs React Components

### *Decorator*

* A function that specifies metadata properties for the component
  * Example: `@Component` creates 3 metadata properties:
    1. `selector`(CSS element selector)
    2. `templateUrl`(location of components template file, HTML file)
    3. `styleUrls`(location of components private CSS styles)
* Like how React imports the css file that styles the component

### *Pipes*

* Transforms data for display(strings, currencies, dates)
* Simple functions used in data binding to transform and return and input value
* Angular provides built-in pipes for common data transformations
* Syntax: uses the `|` (pipe) within interpolation binding to activate function

### *Data Binding*

#### Interpolation Binding

* Syntax: `<h1>{{title}}</h1>`
* Presents the **components** `title` property value inside the HTML tag
* One-way binding?

#### Two-way binding

* Syntax: `[(ngModel)]`
* Binds component property to HTML input. Data can flow from component property to input and from the input back to the property.

### *Directives*

* Extended HTML attributes with the prefix `ng-`
  * Example: `ngFor` repeats the host element for each element in a list (works like .map() does to display multiple elements in React)

### *Templates*

* Templates in Angular are essentially the HTML files associated with their respective components
  * Example: a `heroes.component.ts`(component) will have a corresponding `heroes.component.html`(template)

### *Services*

* A way to share information between classes that don't know each other
* Data that isn't associated with a specific view

### *Dependency Injections*

