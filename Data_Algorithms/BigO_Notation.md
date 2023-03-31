# Algorithms

* Algorithms are a set of instructions to solve a problem.
* Algorithmic thinking is the process of breaking down a problem into smaller problems.

## Table of Contents

* [Time Complexity](#time-complexity)
* [Number of Operations](#number-of-operations)
* [Multiple Operations](#multiple-operations)
* [Space Complexity](#space-complexity)
* [Making Faster Algorithms](#making-faster-algorithms)
* [Greedy Approach](#greedy-approach)


## Time Complexity

Time complexity is the most important thing in algorithms. It is the most important thing to consider when you are designing, choosing and comparing an algorithm. How many primitive operations are performed by an algorithm?

**Think** - As our input size increases, how much time does it take to run an algorithm?

### Number of Operations

* **O(1)** (Fast) - *Constant Time* is the fastest time complexity. It is the fastest. It only needs to access the first element in the array. The amount of time it takes to run an algorithm does not grow with the size of the input data set.
  * Number of operations: 2

  **example**: Accessing the first element in an array is O(1). It only needs to access the first element in the array. If the array is 10 elements long, then 1 operation is performed O(1).

  **example**: string.length - would be O(1) because JavaScript is storing the length of the string in memory. It is not looping through the string to get the length. It is accessing the length property.

* **O(log n)** - *Logarithmic Time* is the second best time complexity. It is faster than linear time, quadratic time, cubic time, and exponential time. It can have different bases. Base 10, Base 2. As your input increases the work(number of operations) decreases by a fraction. Time complexity grows very slow.

  **example**: *Binary search* is O(log n) time complexity. If you have 100 elements, then you only need to perform 7 operations. Every time you loop you only need to work on half of the remaining elements.

* **O(n)** - *Linear Time* It only needs to loop through the input once. The amount of time it takes to run an algorithm grows at a rate of the size of the input data set.
  * Number of operations: 2n

  **example**: When comparing the minium and maximum values in an array, the value for max and minimum is store and compared to the next value in the array. If the next value is greater than the max, then the max is updated. If the next value is less than the min, then the min is updated. 

  **example**: *shift*, *unshift*, *pop*, *push* are all linear time operations. With shift and unshift, the array is shifted to the left or right and each element is moved to the next index. If the array is 10 elements long, then 10 operations are performed O(10).

* **O(n^2)** (Slow) - *Quadratic Time* is the worst time complexity. It is the slowest. It compares every element to every other element. The amount of time it takes to run an algorithm grows at a rate of the square of the size of the input data set.
  * Number of operations: n^2

[Back to top](#algorithms)

### Multiple expressions/loops

* **O(1)**: Running a statement, value lookup on an array, object, or variable.
* **O(log n)**: Loop that cuts the problem in half each time.
* **O(n)**: Loop that iterates through the values of an array once.
* **O(n^2)**: Nested loops(Double).
* **O(n^3)**: Nested loops(Triple).

## Space Complexity

Space complexity is the amount of memory used by an algorithm.

### Things to consider

 * Are you creating new data structures?
 * How often are you doing this in comparison to your input
 * *Call stack*- The call stack is taking place in memory. Something to consider with recursion.

[Back to top](#algorithms)
