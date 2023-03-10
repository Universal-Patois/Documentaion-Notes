# Algorithms

* Algorithms are a set of instructions to solve a problem.
* Algorithmic thinking is the process of breaking down a problem into smaller problems.

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

## Making Faster Algorithms

#### Caching Method
  * Keeping track of things you have already seen (caching). When you see something, save it.
  * Then you can do a property lookup on an object (*O(1)* time complexity)
  * You can take a quadratic time algorithm and make it linear time.

  ```javascript
  // Quadratic time
  const isUnique = (arr) => {
    let result = true;

    for (let i = 0; i < arr.length; i++) {
      for (let j = 0; j < arr.length; j++) {
        if (arr[i] === arr[j] && i !== j) {
          return false;
        }
      }
    }
    return result;
  }

  // Linear time(caching method)
  const isUnique = (arr) => {
    let result = true;
    let cache = {};

    for (let i = 0; i < arr.length; i++) {
      if (cache[arr[i]]) {
        return false;
      } else {
        cache[arr[i]] = true;
      }
    }
    return result;
  }
  ```

### Greedy Approach

* A common algorithmic technique used to solve optimization problems
* It is a greedy algorithm because it makes the best choice at each step as it attempts to find the optimal solution.

#### Can be used to solve:

* Finding minimum or maximum value in an array
* Finding the shortest path in a graph
* Finding the best combination of elements in a set
#### Example

* You are given a set of coins with different values. You are also given a total amount of money. You need to find the minimum number of coins that can be used to make up the total amount of money.

  ```javascript
  const coins = [1, 2, 5, 10, 20, 50, 100, 200];
  const total = 168;

  const greedyApproach = (coins, total) => {
    let result = [];
    let currentTotal = 0;

    for (let i = coins.length - 1; i >= 0; i--) {
      while (currentTotal + coins[i] <= total) {
        result.push(coins[i]);
        currentTotal += coins[i];
      }
    }
    return result;
  }

  greedyApproach(coins, total); // [100, 50, 10, 5, 2, 1]
  ```

### Quick Sort

* version of greedy approach
* selects a pivot element
* sorts the rest of the elements in to two groups based on whether they are less than or greater than the pivot element
* the built-in sort method in JavaScript uses quick sort
## Searching Problems

* Binary search
