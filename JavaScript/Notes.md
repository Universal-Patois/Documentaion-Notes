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

# <r>Notes</r>

## <h2 id='table-of-contents'><o>Table of Contents</o></h2>

* [Comparison Operators](#comparison-operators)
* [Escape Sequences](#escape-sequences)
* [File Path Syntax](#file-path-syntax)
* [Optional Chaining Operator (?.)](#chain-operators)
## <h2 id='comparison-operators'><o>Comparison Operators</o></h2>
In JavaScript, the comparison operators above can also be used to compare strings.
In that case, a dictionary (lexicographical) order is applied.
You can find a list of the exact order of all the characters [here][https://en.wikipedia.org/wiki/List_of_Unicode_characters#Basic_Latin].

```javascript
'Apple' > 'Pear';
// => false

'a' < 'above';
// => true

'a' === 'A';
// => false
```

## <h2 id='equality-comparisons'><o>Equality Comparisons</o></h2>
* <p>=== (strict equality operator)</p>
* <p>== (loose equality operator)</p>
* <p>Object.is()</p>

### <y>Strict Equality Operator (===)</y>
* Strict equality compares two values for equality
* Neither value is implicitly converted to some other value before being compared
* If the values have different types, the values are considered unequal
* Strict equality is almost always the correct comparison operation to use.
* For all values except numbers, it uses the obvious semantics: a value is only equal to itself

```javascript
const num = 0;
const obj = new String("0");
const str = "0";

console.log(num === num); // true
console.log(obj === obj); // true
console.log(str === str); // true

console.log(num === obj); // false
console.log(num === str); // false
console.log(obj === str); // false
console.log(null === undefined); // false
console.log(obj === null); // false
console.log(obj === undefined); // false
```

### <y>Loose Equality Operator (==)</y>
* The loose equality operator compares two values for equality, after converting both values to a common type
* After conversions (one or both sides may undergo conversions), the final equality comparison is performed exactly as === performs it
* Loose equality is symmetric: A == B always has identical semantics to B == A for any values of A and B (except for the order of applied conversions)
* Loose equality is almost always the wrong comparison operation to use
*The result of a comparison using strict equality is easier to predict, and may evaluate more quickly due to the lack of type coercion.

```javascript
const num = 0;
const big = 0n;
const str = "0";
const obj = new String("0");

console.log(num == str); // true
console.log(big == num); // true
console.log(str == big); // true

console.log(num == obj); // true
console.log(big == obj); // true
console.log(str == obj); // true
```

### <y>Object.is()</y>
* The Object.is() method determines whether two values are the same value
* Useful when specific handling of NaN or +0/-0 is needed.
* Provides an alternative to === with different behavior for certain edge cases.
* Treats NaN as equal to NaN, which is different from ===
* Treats +0 and -0 as not equal, unlike ===

```javascript
// === (strict equality operator)
console.log(1 === 1);         // true
console.log('1' === 1);       // false (different types)
console.log(NaN === NaN);     // false
console.log(+0 === -0);       // true

// Object.is()
console.log(Object.is(1, 1));     // true
console.log(Object.is('1', 1));   // false (different types)
console.log(Object.is(NaN, NaN)); // true
console.log(Object.is(+0, -0));   // false
```
 [<h>More on Equality Comparisons</h>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness)

[back to top](#table-of-contents)
## <h2 id='escape-sequences'><o>Escape Sequences</o></h2>

In JavaScript, there are some special characters that are not allowed in strings.
For example, the double quote (`"`) is used to mark the beginning and end of a string.
If you want to include a double quote in a string, you need to escape it with a backslash (`\`).

To accomplish these tasks with little hassle you begin with a backslash ( \ ) within the string, which in essence tells the compiler “Stop! The upcoming text is special.”

### <y>Types of Escape Sequences</y>

There are two types of escape sequences: single-character escape sequences and Unicode escape sequences. The single-character escape sequences are listed below: 

| <h>Escape Sequence</h> | <h>Description<h/> |
| --- | --- |
| <hh>\0</hh> | Null character |
| <hh>\b</hh> | Backspace |
| <hh>\f</hh> | Form feed |
| <hh>\n</hh> | New line |
| <hh>\r</hh> | Carriage return |
| <hh>\t</hh> | Horizontal tab |
| <hh>\'</hh> | Single quote |
| <hh>\"</hh> | Double quote |
| <hh>\\</hh> | Backslash |
| <hh>\a</hh> | Alert (bell) |
| <hh>\s</hh> | Space |

[back to top](#table-of-contents)
### <y>What Each Escape Sequence Does</y>

The following table shows the escape sequences and what they do:

* <h>***Null character***</h>: The null escape sequence adds a null character to the string. This is a character with no value. It is used to terminate a string. It is not visible in the output.

* <h>***Backspace***</h>: The backspace escape sequence moves the cursor back one space. It is used to overwrite the previous character.

* <h>***Form feed***</h>: The form feed escape sequence moves the cursor to the beginning of the next page. It is used to start a new page.

* <h>***New line***</h>: The new line escape sequence moves the cursor to the beginning of the next line. It is used to start a new line.

* <h>***Carriage return***</h>: The carriage return escape sequence moves the cursor to the beginning of the current line.

* <h>***Horizontal tab***</h>: The horizontal tab escape sequence moves the cursor a couple of spaces to the right in the same line.

* <h>***Single quote***</h>: The single quote escape sequence adds a single quote to the string.

* <h>***Double quote***</h>: The double quote escape sequence adds a double quote to the string.

* <h>***Backslash***</h>: The backslash escape sequence adds a backslash to the string.

* <h>***Alert (bell)***</h>: The alert escape sequence makes a sound. It is used to alert the user of something.

* <h>***Space***</h>: The space escape sequence adds a space to the string.

[back to top](#table-of-contents)
## <h2 id='file-path-syntax'><o>File Path Syntax</o></h2>

* The ``..`` syntax means "go up one level in the directory tree".
* So, ``../../`` means "go up two levels in the directory tree", which brings you to the root directory of your project.
* From there, you can reference the assets directory and the ``logo.png`` file using the path ``assets/logo.png``.

## <h2 id='chain-operators'><o>Optional Chaining Operator (?.)</o></h2>

* The optional chaining operator is a feature introduced in JavaScript with the release of ECMAScript 2020
* It provides a concise way to access properties or call functions on an object when there's a possibility that the object or any intermediate property might be nullish or undefined.

### <y>Optional Chaining Benefits</y>

It is beneficial in scenarios where you want to access properties or call methods on objects, but you are uncertain whether the object or any intermediate property along the chain exists or is nullish

1. <h>Avoiding null or undefined errors:</h> 
  * Optional chaining helps prevent errors that would occur if you attempted to access properties or call methods on nullish or undefined values0
  * It allows you to write more defensive code by gracefully handling missing or inaccessible properties.
2. <h>Simplifying conditional checks:</h>
  * Instead of writing verbose and repetitive conditional statements to check the existence of each intermediate property, you can use optional chaining to handle the nullish or undefined values in a more concise manner.
3. <h>Working with optional data:</h>
  * Optional chaining is especially useful when dealing with data that may have optional or nullable fields
  * It allows you to navigate through the data structure without worrying about encountering nullish or undefined values
4. <h>Improving code readability:</h>
  * Optional chaining can make your code more readable by reducing the number of conditional statements and removing unnecessary code
  *  It eliminates the need for lengthy if-else conditions or null checks.

<hh>It's important to note that optional chaining should be used judiciously</hh>
* While it provides convenience and safety in accessing object properties, excessive use of optional chaining might mask potential issues or bugs in your code
* It's essential to consider the context and purpose of your code before deciding to use optional chaining

### <y>Optional Chaining Syntax</y>

#### <g>Example 1</g>

Accessing a Nested Object Property


```javascript
const user = {
  name: 'John',
  address: {
    city: 'New York',
    zipcode: '12345'
  }
};

console.log(user?.address?.city);  // Output: 'New York'
console.log(user?.address?.country);  // Output: undefined

```

In the example above
  * The optional chaining operator allows us to safely access the ``city`` property of the address object even if ``address`` is undefined or nullish
  * If any intermediate property along the chain is undefined or nullish, the result will be ``undefined``


#### <g>Example 2</g>

Accessing an Array Element

```javascript
const arr = [1, 2, 3];

console.log(arr?.[0]);  // Output: 1
console.log(arr?.[5]);  // Output: undefined
```

In the example above
  * The optional chaining operator allows us to safely access the first element of the array even if the array is undefined or nullish
  * By using the optional chaining operator, you can write more robust and concise code that gracefully handles situations where objects or properties might be missing or undefined

#### <g>Example 3</g>

Calling a Function

```javascript
const user = {
  name: 'John',
  greet() {
    console.log(`Hello, ${this.name}!`);
  }
};

user?.greet();  // Output: 'Hello, John!'
user?.age();  // Output: undefined
```

In the example above
  * The optional chaining operator allows us to safely call the ``greet()`` function even if ``user`` is undefined or nullish
  * If ``user`` is undefined or nullish, the result will be ``undefined``
  * If the object is nullish or undefined, the method call is short-circuited and no error is thrown.