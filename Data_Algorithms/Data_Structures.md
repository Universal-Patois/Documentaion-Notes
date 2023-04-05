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

# <r>Common Data Structures</r>

* [Array](#array)
* [Object/Hash](#object)
* [Linked List](#linked-list)
* [Stacks](#stacks)
* [Queues](#queues)
* [Binary Tree](#binary-tree)
* [Graphs](#graphs)

## <o>Learn these three things about each data structure</o>

* What is this data structure really good for?
* What are drawbacks to this data structure?
* When/Where is the data structure most commonly used?

### <y>Array</y>

* Array traversal is a common pattern. You may iterate over each value one-by-one or use a two pointer technique to approach from both ends.

### <y>Object (Hash / Dictionaries)</y>

* Objects can be used to solve problems due to their ability to quickly look-up key-values.
### <y>Linked List</y>

* A linear data structure consisting of a sequence of nodes, where each node contains a data value and a reference to the next node in the sequence
  * <h>**Slightly-linked list-**</h> each node only has reference to its next node
  * <h>**Doubly-linked list-**</h> each node has reference to its next and previous node
* Unlike arrays, which have a fixed size, linked lists can easily grow or shrink as needed 
* Composed of nodes pointing to other nodes which could end up with a node in the list pointing to another node present in the list, leading to an infinite loop

#### <g>What its good for</g>

* For <h>**dynamic data structures**</h> where the size of the data can change over time, as they allow for efficient insertion and deletion of elements
* For implementing <h>**stacks**, **queues**</h>, and other abstract data types
* For situations where you need to efficiently insert or delete elements from the middle of the sequence

#### <g>Drawbacks</g>

* Has a high memory overhead, as each node requires additional reference to the next node
* Traversing a linked list can also be slower than accessing an element in an array, as each node must be visited in order to reach the desired element (unless the node is already known)

#### <g>When/Where is it most commonly used?</g>

* Linked lists are commonly used in situations where the collection of elements needs to be dynamically updated
* They are also commonly used in functional programming languages, which prefer immutable data structures.

##### <b>Example</b>

```javascript
...
```

### <y>Stacks</y>

### <y>Queues</y>

#### <g>What is a Queue?</g>

* <h>*Queue is a FIFO data structure*</h>
  * First in, first out
* <h>*Queue is a linear data structure*</h>
  * Elements are added from one end and removed from the other end
* <h>*A Queue should support two operations*</h>
  * <hh>Enqueue</hh> - Add an element to the end of the queue
  * <hh>Dequeue</hh> - Remove an element from the front of the queue


#### <g>Solutions they solve or are best for</g>

## <o>Common coding challenge types</O>

### <y>Objects (Dictionaries)</y>


### <y>Arrays</y>
Array traversal is a common pattern. You may iterate over each value one-by-one or use a two pointer technique to approach from both ends.

### <y>Strings</y>
These may include finding palindromes, reversal, and other patterns. String problems often incorporate using objects/arrays/etc.

### <y>Dynamic Programming</y>
DP is the process of breaking down a large problem into smaller subproblems and (usually) recursively finding a solution.

### <y>Matrix (2D Arrays)</y>
Matrices can be used to represent a picture (arrays of pixel data) or any other 2D setup (like a geographical map).

### <y>Heaps</y>
Heaps are used for priority queues and other queue-like functionality in programming. They are fast at finding the min/max value of some set of values.





