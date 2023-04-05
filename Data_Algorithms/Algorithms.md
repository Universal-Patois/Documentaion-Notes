<style>
r { color: Crimson }
o { color: Coral }
y { color: Khaki }
g { color: MediumSpringGreen }
b { color: SkyBlue }
i { color: Violet }
h { color:  Plum }
hh { color: Pink }
</style>>
# <h1 <r>Algorithms</r>

* Algorithms are a set of instructions to solve a problem.
* Algorithmic thinking is the process of breaking down a problem into smaller problems.

## <o>Table of Contents</o>
* [Types of Tech Challenges](#types-of-tech-challenges)
* [Greedy Approach](#greedy-approach)
* [Quick Sort](#quick-sort)

## <o>Types of Tech Challenges</o>
### <y>Sorting</y>

* Algorithms used for sorting data
### <y>Searching</y>

### <y>Pattern Matching</y>

### <y>Grids</y>

### <y>Math</y>

### <y>Language Specific</y>

### <y>Optimization</y>
#### <g>Greedy Approach</g>

* A common algorithmic technique used to solve optimization problems
* It is a greedy algorithm because it makes the best choice at each step as it attempts to find the optimal solution.

##### <b>Can be used to solve</b>

* Finding minimum or maximum value in an array
* Finding the shortest path in a graph
* Finding the best combination of elements in a set
###### <i>Example</i>

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

#### <g>Quick Sort</g>

* version of greedy approach
* selects a pivot element
* sorts the rest of the elements in to two groups based on whether they are less than or greater than the pivot element
* the built-in sort method in JavaScript uses quick sort

##### <b>Can be used to solve</b>

* Sorting an array

#### <i>Example</i>

  ```javascript
  const quickSort = (arr) => {
    if (arr.length <= 1) {
      return arr;
    }

    let pivot = arr[arr.length - 1];
    let left = [];
    let right = [];

    for (let i = 0; i < arr.length - 1; i++) {
      if (arr[i] < pivot) {
        left.push(arr[i]);
      } else {
        right.push(arr[i]);
      }
    }
    return [...quickSort(left), pivot, ...quickSort(right)];
  }

  quickSort([4, 2, 5, 1, 3]); // [1, 2, 3, 4, 5]
  ```
