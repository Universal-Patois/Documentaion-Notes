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

# <r>Arrays and Hashing</r>

* Array and hashing problems are often used to sort and search data. They are also used to find duplicates and unique values.
* Hashing is a technique to convert a range of key values into a range of indexes of an array.

## <o>Table of Contents</o>
* [When to use](#when-to-use)
* [Hash Map Method](#unique-sorting-with-caching)
* [Caching with Memoization](#caching-with-memoization)

## <o>When to use</o>
  * Find duplicates
  * Find unique values
  * Sort an array
  * Caching

## <o>Hash Map Method</o>
  * Keeping track of things you have already seen (caching). When you see something, save it.
  * Then you can do a property lookup on an object (<h>*O(1)*</h> time complexity)
  * You can take a quadratic time algorithm and make it linear time.
### <y>Example 1</y>

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
### <y>Example 2</y>

* Transform this simple sorting algorithm into a unique sort. It should not return any duplicate values in the sorted array

  ```javascript
  const input = [4, 2, 2, 3, 2, 2, 2]; // => output: [2, 3, 4]

  const uniqueSort = (arr) => {
    let result = [];
    let cache = {};

    for (let i = 0; i < arr.length; i++) {
      if (!cache[arr[i]]) {
        result.push(arr[i]);
        cache[arr[i]] = true;
      }
    }
    return result.sort((a, b) => a - b);
  }

[Back to top](#table-of-contents)

## <o>Caching with memoization</o>

* Memoization is a technique for caching the results of a function. It is a way to store the results of a function call so that they can be used again later without having to recompute them.

### <y>Example</y>
  ```javascript
  const memoize = (fn) => {
    let cache = {};

    return (...args) => {
      let n = args[0];

      if (n in cache) {
        console.log('Fetching from cache', n);
        return cache[n];
      } else {
        console.log('Calculating result', n);
        let result = fn(n);
        cache[n] = result;
        return result;
      }
    }
  }

  const factorial = memoize(
    (x) => {
      if (x === 0) {
        return 1;
      } else {
        return x * factorial(x - 1);
      }
    }
  );

  factorial(5); // Calculating result 5
  // 120
  factorial(5); // Fetching from cache 5
  // 120
  ```

[Back to top](#table-of-contents)

## <o>Using ES6 Map</o>

* ES6 Map is a data structure that stores key-value pairs. It is similar to an object, but the keys can be any data type
* It is a collection of elements where each element is stored as a Key, value pair
* The keys in Map are ordered while adding the elements to the Map, while keys added to object are not ordered. Thus, when iterating over it, a Map object returns elements in order of insertion.

### <y>Example</y>

```javascript
  var twoSum = (nums, target) => {
  let map = new Map()

  for(let i = 0; i < nums.length; i++) {
    if(map.has(target - nums[i])) {
      return [map.get(target - nums[i]), i]
    } else {
      map.set(nums[i], i)
    }
  }
  return []
}
```