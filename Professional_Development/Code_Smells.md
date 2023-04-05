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
# <r>Code Smells</r>

## <o>Return of boolean should not be wrapped in if/else</o>

 ### <y>Why?</y>
  * The if/else statement is not needed here. The result of the expression is already a boolean.
  * This means that the if/else statement is redundant and can be removed.
  * This makes the code more readable and easier to understand.

 #### <g>Example</g>

```javascript
   if(kind === 'car' || kind === 'truck') {
     return true;
   } else {
     return false;
   }
```

 #### <g>Return of boolean can look like this</g>
  
  ```javascript

  // With double negation
  return !!(kind === 'car' || kind === 'truck');

  // or

  return kind === 'car' || kind === 'truck';
  ```

##### <b>Note that if the result of the expression is not a boolean but for instance an integer, then double negation should be used for proper conversion.</b>

## ``For...of`` <o>loop should be used instead of for loop with iterables(array)</o>

  ### <y>Why?</y>
    If you have an iterable, such as an array, set, or list, your best option for looping through its values is the for of syntax. 
    Use a counter, and …​ well you’ll get the right behavior, but your code just isn’t as clean or clear.

    * The for...of loop is more readable and easier to understand.
    * The for...of loop is more concise and less error prone.
    * The for...of loop is more performant.
  
  #### <g>Example</g>
  
  ```javascript
    const array = [1, 2, 3, 4, 5];
    for (let i = 0; i < array.length; i++) {
      console.log(array[i]);
    }
  ```
  
  #### `For...of` <g>loop can look like this</g>

  ```javascript
    const array = [1, 2, 3, 4, 5];
    for (const element of array) {
      console.log(element);
    }
```
  
##### <b>In a browser environment, NodeList and other array-like collections should work by default. If you are using TypeScript and seeing a type error, make sure your configuration is correct</b>