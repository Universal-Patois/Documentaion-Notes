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
# <r>Angular Notes</r>

## <o>Terminology</o>

* <h>ng</h>: a<h>NG</h>ular

### <y>Modules</y>

* Every Angular app has a root module named `App Module`
* A module is a collection of Angular components, directives, services, pipes, ect...
* They are sharable units with different types
  * system modules(Router)
  * custom modules
  * third party modules(ngrx, rxjs)
* These modules can be lazy-loaded. Meaning they only get loaded when they are needed. Improving performance
* Many modules make of an application

### <y>Components</y>

* Is the most basic building block of UI in an Angular app
* Controls a parch of screen called a view
* Display data on the screen, listen for user input, and take action on input
* Can use other components declared within the same module
* For components outside its module they need to be exported from that module and imported into the module that needs the functionality
* Should not fetch or save data directly - only focus on presenting data and delegate data access to a *service*

#### <g>Angular components vs React Components</g>

### <y>Decorator</y>

* A function that specifies metadata properties for the component
  * <h>Example</h>: `@Component` creates 3 metadata properties:
    1. `selector`(CSS element selector)
    2. `templateUrl`(location of components template file, HTML file)
    3. `styleUrls`(location of components private CSS styles)
* Like how React imports the css file that styles the component

### <y>Pipes</y>

* Transforms data for display(strings, currencies, dates)
* Simple functions used in data binding to transform and return and input value
* Angular provides built-in pipes for common data transformations
* Syntax: uses the `|` (pipe) within interpolation binding to activate function

### <y>Data Binding</y>

#### <g>Interpolation Binding</g>

* <h>Syntax</h>: `<h1>{{title}}</h1>`
* Presents the **components** `title` property value inside the HTML tag
* One-way binding?

#### <g>Two-way binding</g>

* <h>Syntax</h>: `[(ngModel)]`
* Binds component property to HTML input. Data can flow from component property to input and from the input back to the property.

### <y>Directives</y>

* Extended HTML attributes with the prefix `ng-`
  * <h>Example</h>: `ngFor` repeats the host element for each element in a list (works like .map() does to display multiple elements in React)

### <y>Templates</y>

* Templates in Angular are essentially the HTML files associated with their respective components
  * <h>Example</h>: a `heroes.component.ts`(component) will have a corresponding `heroes.component.html`(template)

### <y>Services</y>

* A way to share information between classes that don't know each other
* Data that isn't associated with a specific view

### <y>Dependency Injections</y>

