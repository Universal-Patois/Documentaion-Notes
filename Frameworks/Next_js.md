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

# <h1 id='next-13'><r>Next 13</r></h1>

* Next.js is a framework built on top of React, offering several advantages over using React alone

## <h2 id='table-of-contents'><o>Table of Contents</o></h2>
- [<l>What Next.js Offers</l>](#what-nextjs-offers)
- [<l>CSS Styling</l>](#css-styling)
- [<l>Optimization</l>](#optimization)
- [<l>Creating Layouts and Pages</l>](#creating-layouts-and-pages)
- [<l>Navigation</l>](#navigation)
- [<l>Setting up a Database</l>](#setting-up-a-database)
- [<l>Fetching Data</l>](#fetching-data)
- [<l>Static and Dynamic Rendering</l>](#static-and-dynamic-rendering)
- [<l>Streaming and Prerenedering</l>](#streaming-and-prerenedering)
- [<l>Search and Pagination</l>](#search-and-pagination)
- [<l>Mutating Data</l>](#mutating-data)
- [<l>Handling Errors</l>](#handling-errors)
- [<l>Accessibility</l>](#accessibility)
- [<l>Authentication</l>](#authentication)
- [<l>Metadata</l>](#metadata)

## <h2 id='what-nextjs-offers'><o>What Next.js Offers</o></h2>

* <h>Server-side Rendering(SSR)</h>
    * Provides built-in support for server-side rendering, which improves performance and SEO by generating HTML on the server and sending it to the client.
    * This results in faster initial page loads and better search engine indexing compared to client-side rendering.

* <h>Static Site generation(SSG)</h>
    * It supports static site generation, which allows you to pre-render pages at build time and serve them as static files.
    * This is useful for content that doesn't change frequently, such as marketing pages, blogs, or documentation.
    * This is beneficial for content-heavy websites or pages with relatively static content, as it reduces server load and improves scalability.

* <h>Automatic Code Splitting</h>
    * It automatically splits code into smaller chunks, which ensures that only the necessary code is loaded for each page.
    * This helps reduce the initial page load time and improves performance, especially for larger applications or slower connections.

* <h>File-based Routing</h>
    * Simplifies routing by using a file-based system, where each page is represented by a file.
    * You can create pages by adding JavaScript files to the `pages` directory making it intuitive to organize and navigate application routes.

* <h>API Routes</h>
    * It allows you to create API routes alongside your pages, enabling you to build backend functionality within the same framework. 
    * This simplifies the development process by providing a unified solution for both client-side and server-side code.

* <h>Automatic Static Optimization</h>
    * It optimizes your application for production by automatically optimizing images, CSS, and JavaScript files.
    * This helps improve performance and reduces the need for manual optimizations.

* Built-in CSS Support
    * It supports various CSS methodologies, including CSS Modules, CSS-in-JS libraries like styled-components, and global CSS files out of the box.
    * This flexibility allows you to choose the CSS approach that best fits your project's needs.

* <h>TypeScript Support</h>
    * It has built-in TypeScript support, making it easy to use TypeScript for static typing and improved developer productivity.
  
* <h>Incremental Static Regeneration(ISR)</h>
    * A feature that allows you to update static content at runtime without rebuilding the entire site.
    * This enables real-time updates for dynamic content while still benefiting from the performance advantages of static site generation.

[Back to Top](#next-13)

### <y>Why Use Next.js Over React?</y>
* <h>Need for Server-Side Rendering (SSR) or Static Site Generation (SSG)</h> 
    * If your project requires server-side rendering or static site generation for improved performance, SEO, or handling of dynamic data, Next.js provides built-in support for these features. 
    * React alone doesn't offer SSR or SSG out of the box, so Next.js would be a better choice in such cases.

* <h>Simplified Routing and Configuration</h>
    * If you prefer a simpler approach to routing and configuration, Next.js's file-based routing system and built-in configurations can save you time and effort compared to setting up routing manually with React.

* <h>Built-in API Routes</h>
  * If your project requires backend functionality or API routes alongside your frontend code, Next.js's built-in API routes streamline the development process by providing a unified solution within the same framework.

* <h>TypeScript Support</h>
    * If you prefer using TypeScript for static typing and improved developer productivity, Next.js offers built-in TypeScript support, making it easier to integrate TypeScript into your project compared to setting it up manually with React.

### <y>When to Use React Instead of Next.js?</y>
* <h>Simple Single-Page Applications (SPAs)</h>
    * If your project is a simple single-page application without the need for server-side rendering, static site generation, or complex routing, React might be a more lightweight option that meets your requirements without the additional overhead of Next.js.

* <h>Customized Configuration</h>
    * If you need more control over your project's configuration and prefer to set up routing, webpack, and other configurations manually or use custom setups, React allows for more flexibility in configuring your project compared to the more opinionated approach of Next.js.

* <h>Existing Project Structure</h>
    * If you already have an existing React project with a specific project structure, build setup, or dependencies in place and don't require the features provided by Next.js, it might be more convenient to continue using React rather than migrating to Next.js.

* <h>Preference for Modularization</h>
    * If you prefer a more modular approach where you can selectively choose and integrate libraries, tools, and configurations based on your project's specific needs.
    * React provides a more modular and customizable ecosystem compared to the integrated features of Next.js.

[Back to Top](#next-13)

## <h2 id='css-styling'><o>CSS Styling</o></h2> 
* Next.js provides built-in support for various CSS methodologies, including CSS Modules, Tailwind CSS, and global CSS files.
* Tailwind and CSS modules are the two most common ways of styling Next.js applications. Whether you use one or the other is a matter of preference - you can even use both in the same application
    * [Styling Documentation](https://nextjs.org/docs/pages/building-your-application/styling)

### <y>Global Styles</y>
* You can use the ```global.css``` file to add CSS rules to all the routes in your application - such as CSS reset rules, site-wide styles for HTML elements like links, and more.
* You can import global.css in any component in your application, but it's usually good practice to add it to your top-level component.
* In Next.js, this is the [root layout](https://nextjs.org/docs/app/building-your-application/routing/pages-and-layouts#root-layout-required).

### <y>Tailwind CSS</y>
* Next.js has built-in support for Tailwind CSS, a utility-first CSS framework that allows you to rapidly build custom designs.
* It speeds up the development process by allowing you to quickly write [utility classes](https://tailwindcss.com/docs/utility-first) directly in your TSX markup.
* In Tailwind, you style elements by adding class names.
* Although the CSS styles are shared globally, each class is singularly applied to each element.
    * This means if you add or delete an element, you don't have to worry about maintaining separate stylesheets, style collisions, or the size of your CSS bundle growing as your application scales.

#### <g>Example</g>
```tsx
<h1 className="text-blue-500">I'm blue!</h1>
```
    * In this example, the text color of the h1 element is set to blue using the Tailwind CSS class text-blue-500.

[More on Tailwind CSS](https://tailwindcss.com/)

### <y>CSS Modules</y>
* CSS Modules allow you to scope CSS to a component by automatically creating unique class names, so you don't have to worry about style collisions as well.

### <y>Using the ```clsx``` Library</y>
* There may be cases where you may need to conditionally style an element based on state or some other condition.
* The [clsx](https://www.npmjs.com/package/clsx) is a library that lets you toggle class names easily. 

[clsx documentation](https://github.com/lukeed/clsx)

#### <g>Example</g>
```tsx
import clsx from 'clsx';
 
export default function InvoiceStatus({ status }: { status: string }) {
  return (
    <span
      className={clsx(
        'inline-flex items-center rounded-full px-2 py-1 text-sm',
        {
          'bg-gray-100 text-gray-500': status === 'pending',
          'bg-green-500 text-white': status === 'paid',
        },
      )}
    >
    // ...
)}
```
    * Suppose that you want to create an InvoiceStatus component which accepts status. The status can be 'pending' or 'paid'.
    * If it's 'paid', you want the color to be green. If it's 'pending', you want the color to be gray.

[Back to Top](#next-13)

## <h2 id='optimization'><o>Optimization</o></h2>

