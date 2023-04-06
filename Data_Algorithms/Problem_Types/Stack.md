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

# <h1 id='stack'><r>Stack</r></h1>
* A stack data structure is a linear data structure that follows the principle of Last In First Out (LIFO)
* It is a collection of elements that are added and removed from the same end of the structure
* The end of the stack is called the top and the opposite end is called the base
## <h2 id='table-of-contents'><o>Table of Contents</o></h2>
* [<l>When to Use</l>](#when-to-use)
* [<l>Drawbacks</l>](#drawbacks)
* [<l>How to Use</l>](#how-to-use)

## <h2 id='when-to-use'><o>When to Use</o></h2>

### <y>Problems they are good for solving</y>
* Used to reverse a string
* Used to check if a string is a palindrome
* Used to check if a string has balanced parentheses

### <y>Most commonly seen in</y>
* Problems that involve last in first out behavior
* Managing function calls in a program
* Managing undo/redo functionality in a program
* Managing memory allocation
* Parsing expressions
* It can also be used for
    * Depth-first searching in graphs
    * Backtracking
    * Infix to postfix conversions
## <h2 id='drawbacks'><o>Drawbacks</o></h2>
* The stack is limited in size and speed
* It has limited access to its elements
* Only the top of the stack can be accessed at any given time
    * Modifying elements in the middle of the stack requires removing all elements above it
    * This can be inefficient in cases where frequent access of non-top elements is required
* It can be susceptible to stack overflow
    * This occurs because the stack is implemented using a fixed size array or a linked list
    * Stack overflow occurs when the stack is full and an element is pushed onto it
### <y>Advantages</y>
* Really good for solving problems that involve last in first out behavior

[Back to Top](#table-of-contents)

## <h2 id='how-to-use'><o>How to Use</o></h2>
1. <i>Create an empty stack</i>
    * This can be done by creating an empty array
2. <i>Loop through each index of the array</i>
3. <i>Push the element that is at the current index onto the stack</i>
    * This can be done by using the push method
4. <i>Check if the current character matches the top element in the stack</i>
    * If the element matches, pop the top element off the stack
5. <i>Return true if the stack is empty</i>
    * This means that all the conditions were meet with the problem
    * If the stack is not empty, return false
    * This means that all the conditions were not meet with the problem

### <y>Examples</y>
* Write a function that takes a string of parentheses, brackets, and curly braces as input and returns true if the parentheses are properly nested and false otherwise.
```javascript
  var isValid = function(s) {   
    const stack = [];
    const map = {
      '(': ')',
      '[': ']',
      '{': '}'
    }
    
    for (let i = 0 ; i < s.length ; i++) {
        let c = s[i];
        if (map[c]) {
          stack.push(map[c])
        } else if (c !== stack.pop()) {
          return false;
        } 
    }
    
    return stack.length === 0;
};
```

```javascript
    var isValid = function(s) {   
    const stack = [];
    
    for (let i = 0 ; i < s.length ; i++) {
        let c = s.charAt(i);
        switch(c) {
            case '(': stack.push(')');
                break;
            case '[': stack.push(']');
                break;
            case '{': stack.push('}');
                break;
            default:
                if (c !== stack.pop()) {
                    return false;
                }
        }
    }
    
    return stack.length === 0;
};
```


[Back to Top](#table-of-contents)
