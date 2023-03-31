# Common Data Structures

* [Array](#array)
* [Object/Hash](#object)
* [Linked List](#linked-list)
* [Stacks](#stacks)
* [Queues](#queues)
* [Binary Tree](#binary-tree)
* [Graphs](#graphs)

## Learn these three things about each data structure

* What is this data structure really good for?
* What are drawbacks to this data structure?
* When/Where is the data structure most commonly used?

### Array

* Array traversal is a common pattern. You may iterate over each value one-by-one or use a two pointer technique to approach from both ends.

### Object (Hash / Dictionaries)

* Objects can be used to solve problems due to their ability to quickly look-up key-values.
### Linked List

* A linear data structure consisting of a sequence of nodes, where each node contains a data value and a reference to the next node in the sequence
  * **Slightly-linked list-** each node only has reference to its next node
  * **Doubly-linked list-** each node has reference to its next and previous node
* Unlike arrays, which have a fixed size, linked lists can easily grow or shrink as needed 

#### What its good for

* For **dynamic data structures** where the size of the data can change over time, as they allow for efficient insertion and deletion of elements
* For implementing **stacks**, **queues**, and other abstract data types
* For situations where you need to efficiently insert or delete elements from the middle of the sequence

#### Drawbacks

* Has a high memory overhead, as each node requires additional reference to the next node
* Traversing a linked list can also be slower than accessing an element in an array, as each node must be visited in order to reach the desired element (unless the node is already known)

#### When/Where is it most commonly used?

* Linked lists are commonly used in situations where the collection of elements needs to be dynamically updated
* They are also commonly used in functional programming languages, which prefer immutable data structures.

#### Example

```javascript
...
```

### Stacks

### Queues

#### What is a Queue?

* *Queue is a FIFO data structure*
  * First in, first out
* *Queue is a linear data structure*
  * Elements are added from one end and removed from the other end
* *A Queue should support two operations*
  * Enqueue - Add an element to the end of the queue
  * Dequeue - Remove an element from the front of the queue


### solutions they solve or are best for

## Common coding challenge types

### Objects (Dictionaries)


### Arrays
Array traversal is a common pattern. You may iterate over each value one-by-one or use a two pointer technique to approach from both ends.

### Strings
These may include finding palindromes, reversal, and other patterns. String problems often incorporate using objects/arrays/etc.

## Dynamic Programming
DP is the process of breaking down a large problem into smaller subproblems and (usually) recursively finding a solution.

## Matrix (2D Arrays)
Matrices can be used to represent a picture (arrays of pixel data) or any other 2D setup (like a geographical map).

## Heaps
Heaps are used for priority queues and other queue-like functionality in programming. They are fast at finding the min/max value of some set of values.





