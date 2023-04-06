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
# <r>Loops</r>
* Loops are used to repeat a block of code until a certain condition is met.
## <o>Table of Contents</o>

* [<l>While Loops</l>](#while-loops)
* [<l>Do..while Loops</l>](#dowhile-loops)
* [<l>For..in Loops</l>](#forin-loops)
* [<l>For..of Loops</l>](#forof-loops)
* [<l>Switch Statements</l>](#switch-statements)

## <o>Keep in Mind</o>
* Inside a loop body, you can use the `break` keyword to stop the execution of the loop entirely.
* The keyword `continue` only stops the execution of the current iteration and continues with the next one.
* With `continue` you can often avoid wrapping big parts of the loop body in an if-statement.
## <h2 id="while-loops"><o>While Loops</o></h2>
* With a while loop, you can execute code repeatably as long as a certain condition is fulfilled.
* It is written with the `while` keyword followed by a condition wrapped in round brackets and a code block that contains the _body_ of the loop wrapped in curly brackets.

### <y>Syntax</y>
```javascript
while (condition) {
  // code
  // so-called "loop body"
}
```

#### <g>Example</g>
```javascript
  let i = 0;

  while (i < 100) {
    i = i + 2;

    if (i % 3 === 0) {
      continue;
    }

    // The code here will only be executed when i was not divisible
    // by 3 in the check above.
  }
```

[Back to Top](#table-of-contents)

## <h2 id="dowhile-loops"><o>Do..while Loops</o></h2>
* The condition is checked after the loop body was executed.
* This is useful when the condition depends on evaluations done in the body.

### <y>Syntax</y>
```javascript
do {
  // code
  // so-called "loop body"
} while (condition);
```

#### <g>Example</g>
```javascript
function getUserInput() {
  let input;
  do {
    input = prompt("Please enter a whole number:");
  } while (isNaN(input) || parseInt(input) !== parseFloat(input));
  return parseInt(input);
}

```

[Back to Top](#table-of-contents)
## <h2 id="forin-loops"><o>For..in Loops</o></h2>
There is a special `for...in` loop to iterate over all keys of an object.

### <y>Syntax</y>
```javascript
for (key in object) {
  // code
  // so-called "loop body"
}
```

#### <g>Example</g>
```javascript
  const obj = {
    name: 'Ali',
    age: 65,
  };

  for (let key in obj) {
    console.log(key, obj[key]);
  }
  // name Ali
  // age 65
```

* To avoid subtle errors, you should always assume the `for...in` loop visits the keys in an arbitrary order.
* Also, be aware that `for...in` includes inherited keys in its iteration.

[Back to Top](#table-of-contents)

## <h2 id="forof-loops"><o>For..of Loops</o></h2>
* The `for...of` loop is used to iterate over the elements of an iterable objects like `Array`, `Map`, `Set`, `String`, `TypedArray`, `arguments` object and so on.
* When you want to work with the value directly in each iteration and do not require the index at all, you can use a `for...of` loop.
* `for...of` works like the basic for loop shown above, but instead of having to deal with the index as a variable in the loop, you are provided with the value directly.

### <y>Syntax</y>
```javascript
for (variable of iterable) {
  statement;
}
```
#### <g>Example</g>
```javascript
const arr = [1, 2, 3];

for (let element of arr) {
  console.log(element);
}
```

[Back to Top](#table-of-contents)

## <h2 id="switch-statements"><o>Switch Statements</o></h2>
* It is used when a single variable needs to be compared to multiple variants.
* The comparison is done by checking for strict equality (`===`)
* For some variable `x`, the switch statement in JavaScript has the following syntax.


### <y>Syntax</y>
```javascript
  switch (x) {
    case option1:
      // code that is executed when "x === option1" is true
      break;
    case option2:
      // code that is executed when "x === option2" is true
      break;
    default:
      // code that is executed when x does not equal any of the options
  }
```

#### <g>Example</g>
```javascript
  const x = 2;

  switch (x) {
    case 1:
      console.log('x is 1');
      break;
    case 2:
      console.log('x is 2');
      break;
    default:
      console.log('x is not 1 or 2');
  }
```

* The `default` case is optional and used in case you want to execute some code if none of the other options match the variable.
*The `break` statements above are needed because by default all cases are "fallthrough" in JavaScript.
* Without any `break` statement all the code in the cases below the first matching option would be executed even though `x` did not match those options.
* This <h>fallthrough by default</h> behavior is a common pitfall when using `switch` in JavaScript.
* Inside a function, `return` can also be used instead of `break` to avoid this problem.

[Back to Top](#table-of-contents)
