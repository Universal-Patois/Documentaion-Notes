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

# <r>Linked List</r>

* A linked list is a linear data structure that stores data in nodes

## <h2 id='table-of-contents'><o>Table of Contents</o></h2>
* [<l>When to use</l>](#when-to-use)
* [<l>Drawbacks</l>](#drawbacks)
* [<l>How to use</l>](#how-to-use)

## <h2 id='when-to-use'><o>When to Use</o></h2>
* When implementing dynamic data structures where the size of the data structure can change during program execution
* Situations where the size of the data structure is not known in advance or can change dynamically

### <y>Problems they are good for solving</y>
* Adding or removing elements from a list frequently

### <y>Most commonly seen in</y>
* Web browsers *(for storing history of visited pages)*
* File systems *(for storing files and directories)*
* Text editors *(for storing undo/redo history)*
* Computer games *(for managing object lists)*

## <h2 id='drawbacks'><o>Drawbacks</o></h2>
* Linked lists do not provide direct access to the elements in the list
    * You must start at the head of the list and traverse the list until you reach the desired element
    * This is makes operations like  searching for a specific element less efficient than with other data structures
    * This is why linked lists are not commonly used for searching, retrieving, sorting operations, or random access
* Linked lists require more memory than arrays because each element in the list must store a pointer to the next element in the list

### <y>Advantages</y>
* Efficiently add or remove elements from the list regardless of the size of the list
    * Linked lists only require a few simple pointer manipulations to add or remove elements
    * Unlike <h>arrays</h> where inserting or deleting an element requires shifting all the elements in the array

[Back to Top](#table-of-contents)

## <h2 id='how-to-use'><o>How to Use</o></h2>
1. <i>Define a node class</i>
    * Each node in the list must store the data and a pointer to the next node in the list
    * The last node in the list must point to null
2. <i>Define a linked list class to represent the linked list</i>
    * The list should contain a head element that points to the first node in the list
3. <i>Define a method to add a new node to the list</i>
    * The new node should be added to the beginning of the list
    * The new node should point to the current head of the list
    * The head of the list should be updated to point to the new node
4. <i>Define a method to remove a node from the list</i>
    * The node to be removed should be the first node in the list
    * The head of the list should be updated to point to the second node in the list
    * The node to be removed should be returned
5. <i>Test the linked list by creating a new instance and pushing and popping elements from the stack</i>

### <y>Example</y>
* Implement a stack data structure using a linked list
```javascript
  class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

class LinkedList {
  constructor() {
    this.head = null;
  }
}

// Add a new node to the beginning of the list
class LinkedList {
  // ...

  push(value) {
    const node = new Node(value);
    node.next = this.head;
    this.head = node;
  }
}

// Remove the first node from the list
class LinkedList {
  // ...

  pop() {
    if (!this.head) {
      return null;
    }
    const value = this.head.value;
    this.head = this.head.next;
    return value;
  }
}

// Test the linked list 
const stack = new LinkedList();
stack.push(1);
stack.push(2);
stack.push(3);
console.log(stack.pop()); // 3
console.log(stack.pop()); // 2
console.log(stack.pop()); // 1
console.log(stack.pop()); // null
```

[Back to Top](#table-of-contents)

### <y>Example</y>

* Given the head of a slightly linked list, reverse that list, and return the reversed list

#### <g>Iterative Solution</g>
```javascript
  let reverseList = function(head) {
    let previous = null;
    let current = head;
    while