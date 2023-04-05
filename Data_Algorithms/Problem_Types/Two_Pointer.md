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

# <h1 id='two-pointer-technique'><r>Two Pointer Technique</r></h1>
* Two pointer problems are a type of problem where you have a list of elements and you need to find a pair of elements that satisfy a certain condition.
* These problems consist of comparing values at the two pointers
* The most famous usages are the `Fast/Slow` pointers and the `Start/End`(`Left`/`Right`) pointer techniques
* The two pointer problem is excellent for:
  * Working with pairs
  * Separating data
  * Finding ranges(or subsequences) in sequences
  * Finding a cycle in a linked list
* The most famous
## <h2 id='table-of-contents'><o>Table of Contents</o></h2>
* [<l>When to use</l>](#when-to-use)
* [<l>Drawbacks</l>](#drawbacks)
* [<l>How to Use</l>](#how-to-use)
* [<l>Things to Think About</l>](#things-to-think-about-when-making-a-two-pointer-algorithm)
* | **[<l>Types of Two Pointer Techniques</l>](#types-of-two-pointer-techniques)** |
  | --------------------------------- |
  | *[Two Pointers Approach](#two-pointers-approach)* |
  | *[Sliding Window Technique](#sliding-window-technique)* |
  | *[Two Pointers with Hash Table](#two-pointers-with-hash-table)* |
* | **[<l>Types of Two Pointer Problems</l>](#types-of-two-pointer-problems)** |
  | --------------------------------- |
  | *[Searching for a pair of elements in a sorted array](#searching-for-a-pair-of-elements-in-a-sorted-array)* |
  | *[Remove Duplicates from Sorted Array](#remove-duplicates-from-sorted-array)* |
  | *[Check if a string is a palindrome](#check-if-a-string-is-a-palindrome)* |
  | *[Find the longest substring that is a palindrome](#find-the-longest-substring-that-is-a-palindrome)* |
  | *[Find the intersection of two sorted arrays](#find-the-intersection-of-two-sorted-arrays)* |
  | *[Find the smallest subarray in a given array that has a given sum](#find-the-smallest-subarray-in-a-given-array-that-has-a-given-sum)* |
  | *[Find the maximum sum of a subarray of a given array](#find-the-maximum-sum-of-a-subarray-of-a-given-array)* |
## <o>When to use<o/>

The two pointer technique is a useful and versatile algorithmic pattern that can be applied to a wide range of problems, particularly those involving ```arrays``` and ```linked lists```

### <y>Problems they are good for solving</y>

* Searching for a pair of elements in a sorted array
* Removing duplicates from a sorted array
* Checking whether a given string is a palindrome
* Finding the longest substring that is a palindrome(or substring without repeating characters)
* Finding the intersection of two sorted arrays
* Finding the smallest subarray in a given array that has a given sum
* Finding the maximum sum of a subarray of a given array
* Finding pairs of elements that add up to a certain value

### <y>Most commonly seen in</y>
* Finding pairs in an array that sum to a given target value
* Finding the longest substring without repeating characters in a string

## <h2 id='drawbacks'><o>Drawbacks</o></h2>
* May not be suitable for all types of problems
* Can be difficult to implement correctly
### <y>Advantages</y>
* Its time complexity is often <hh>linear( O(n) )</hh> or <hh>linearithmic( O(n log n) )</hh>
* It does not require any extra space for storage making it memory efficient
* Particularly useful when the problem requires comparing elements of the array or linked list to each other in some way
    * Such as finding pairs of elements that add up to a certain value or finding the longest substring without repeating characters
## <h2 id='how-to-use'><o>How to Use</o></h2>
1. <i>**Identify the problem**</i>
    * Identify that th problem can be solved using the two-pointer technique
2. <i>**Identify the pointers**</i>
    * Initialize two pointers, typically called <h>left</h> and <h>right</h>, at the beginning and end of the array or string
3. <i>**Set Conditions**</i>
    * Set the conditions for moving the pointers
    * These conditions are based on the problem you are trying to solve
4. <i>**Loop through the array or string**</i>
    * Loop through the array or string while the pointers meet the conditions(`While loop` is usually used)
5. <i>**Update the pointers**</i>
    * Update the pointers based on the conditions
6. <i>**Return the result**</i>
    * Return the result of the problem based on the conditions that were set
## <o>Things to think about when making a two pointer algorithm</o>
* <h>**Starting Point**</h> - Where pointers 1 and 2 should be located. 
  * Both in the beginning?
  * Both at the end?
  * One at each end?
  * Middle?

* <h>**Speed**</h> - How fast should the pointers move?
  * At the same speed?
  * One faster than the other?
  * Moving only one pointer at a time?

* <h>**Stop Conditions**</h> - When should the algorithm stop?
  * When the pointers meet?
  * When one pointer reaches the end?
  * Loop until the end of the array?
  * When the pointers reach a certain value?

[Back to Top](#table-of-contents)
## <h2 id='types-of-two-pointer-techniques'><o>Types of Two Pointer Techniques</o></h2>

### <h3 id='two-pointers-approach'><y>Two Pointers Approach</y></h3>
* <hh>**Usually starting from the beginning and end of an array or list, and moving them towards each other until they meet**</hh>
* It is often used to solve problems related to <h>**searching or sorting**</h>
* Can be used to reduce the time complexity of an algorithm from O(n^2) to O(n)

#### <g>Example</g>
* Given an array of integers and a target sum, find a pair of numbers in the array that add up to the target sum
```javascript
  function findPairWithTargetSum(arr, targetSum) {
  arr.sort((a, b) => a - b); // sort the input array in ascending order
  let left = 0; // initialize left pointer
  let right = arr.length - 1; // initialize right pointer

  while (left < right) {
    const currentSum = arr[left] + arr[right];
    if (currentSum === targetSum) {
      return [arr[left], arr[right]]; // found the pair
    } else if (currentSum < targetSum) {
      left++; // move the left pointer to the right
    } else {
      right--; // move the right pointer to the left
    }
  }

  return [-1, -1]; // pair not found
}

// example usage
const arr = [8, 4, 2, 6, 10];
const targetSum = 10;
const result = findPairWithTargetSum(arr, targetSum);
console.log(result); // expected output: [4, 6]
```

[Back to Top](#table-of-contents)

### <h3 id='sliding-window-technique'><y>Sliding Window Technique</y></h3>
* <hh>**Usually starting at the beginning of an array or list, and moving one or both of them in a specific direction to create a window or subarray**</hh>
* It is often used to solve problems related to <h>**substring or subarray manipulation**</h>
* Can be used to reduce the time complexity of an algorithm from O(n^2) to O(n)

#### <g>Example</g>
* Given a string and a pattern, find the smallest substring in the string that contains all the characters in the pattern
```javascript
  function findSubstring(str, pattern) {
  const charCounts = {};
  let left = 0;
  let right = 0;
  let count = 0;
  let minLength = str.length + 1;
  let minSubstring = '';

  for (const char of pattern) {
    charCounts[char] = charCounts[char] ? charCounts[char] + 1 : 1;
  }

  while (right < str.length) {
    const rightChar = str[right];
    if (charCounts[rightChar]) {
      count++;
    }
    charCounts[rightChar] = charCounts[rightChar] ? charCounts[rightChar] - 1 : -1;
    right++;

    while (count === pattern.length) {
      if (right - left < minLength) {
        minLength = right - left;
        minSubstring = str.slice(left, right);
      }
      const leftChar = str[left];
      if (charCounts[leftChar] === 0) {
        count--;
      }
      charCounts[leftChar] = charCounts[leftChar] + 1;
      left++;
    }
  }

  return minSubstring;
}

```

[Back to Top](#table-of-contents)

### <h3 id='two-pointers-with-hash-table'><y>Two Pointers with Hash Table</y></h3>
* This technique involves using two pointers and a hash table to efficiently solve problems that require **tracking the occurrence or frequency of elements in an array or list**
* It is often used to reduce the time complexity of an algorithm from O(n^2) to O(n).

#### <g>Example</g>
* Given an array of integers and a target sum, find all pairs of numbers in the array that add up to the target sum
```javascript
  function findPairs(array, targetSum) {
  const pairs = [];
  const hashTable = {};
  
  for (let i = 0; i < array.length; i++) {
    const complement = targetSum - array[i];
    
    if (hashTable[complement]) {
      pairs.push([complement, array[i]]);
    }
    
    hashTable[array[i]] = true;
  }
  
  return pairs;
}

const array = [3, 4, 2, 5, 6, -1, 8, 7, 1, 9];
const targetSum = 7;

const pairs = findPairs(array, targetSum);
console.log(pairs); // [[4, 3], [2, 5], [-1, 8], [1, 6]]
```

[Back to Top](#table-of-contents)
## <h2 id='types-of-two-pointer-problems'><o>Types of Two Pointer Problems</o></h2>

### <h3 id='searching-for-a-pair-of-elements-in-a-sorted-array'><y>Searching for a pair of elements in a sorted array</y></h3>
#### <g>Example</g>
```javascript
  function findPair(arr, targetSum) {
  let left = 0;
  let right = arr.length - 1;

  while (left < right) {
    const sum = arr[left] + arr[right];
    if (sum === targetSum) {
      // Found the pair!
      return [arr[left], arr[right]];
    } else if (sum < targetSum) {
      // Need a bigger sum, move the left pointer to the right
      left++;
    } else {
      // Need a smaller sum, move the right pointer to the left
      right--;
    }
  }

  // Couldn't find a pair with the target sum
  return null;
}

const arr = [1, 3, 5, 7, 9];
const targetSum = 8;

const pair = findPair(arr, targetSum);

if (pair) {
  console.log(`Pair found: ${pair[0]} + ${pair[1]} = ${targetSum}`);
} else {
  console.log(`No pair found with sum ${targetSum}`);
}
```

[Back to Top](#table-of-contents)
### <h3 id='remove-duplicates-from-sorted-array'><y>Remove Duplicates from Sorted Array</y></h3>
#### <g>Example</g>
```javascript
  function removeDuplicates(nums) {
  if (nums.length === 0) {
    return 0;
  }
  
  let i = 0;
  
  for (let j = 1; j < nums.length; j++) {
    if (nums[i] !== nums[j]) {
      i++;
      nums[i] = nums[j];
    }
  }
  
  return i + 1;
}

const nums = [1, 1, 2, 2, 3, 4, 5, 5, 5];
const newLength = removeDuplicates(nums);
console.log(nums.slice(0, newLength)); // Output: [1, 2, 3, 4, 5]
```

[Back to Top](#table-of-contents)
### <h3 id='check-if-a-string-is-a-palindrome'><y>Check if a string is a palindrome</y></h3>
#### <g>Example</g>

```javascript
  var isPalindrome = function(string) {
      let concatedString = string.toLowerCase().replace(/[^a-zA-Z0-9]/gi,'')
  for (let i = 0, j = concatedString.length - 1; i <= j; i++, j--) {
      if(concatedString.charAt(i) !== concatedString.charAt(j)) return false
  }
      console.log(concatedString)
      return true
  };
```

### <h3 id='find-the-longest-substring-that-is-a-palindrome'><y>Find the longest substring that is a palindrome</y></h3>
#### <g>Example</g>
```javascript
  function longestPalindrome(s) {
  let longest = '';
  
  for (let i = 0; i < s.length; i++) {
    // Check for odd length palindromes with center at i
    let left = i, right = i;
    while (left >= 0 && right < s.length && s[left] === s[right]) {
      let palindrome = s.substring(left, right + 1);
      if (palindrome.length > longest.length) {
        longest = palindrome;
      }
      left--;
      right++;
    }
    
    // Check for even length palindromes with center at i and i + 1
    left = i, right = i + 1;
    while (left >= 0 && right < s.length && s[left] === s[right]) {
      let palindrome = s.substring(left, right + 1);
      if (palindrome.length > longest.length) {
        longest = palindrome;
      }
      left--;
      right++;
    }
  }
  
  return longest;
}

console.log(longestPalindrome('babad')); // Output: 'bab'
console.log(longestPalindrome('cbbd')); // Output: 'bb'
```
[Back to Top](#table-of-contents)

### <h3 id='find-the-intersection-of-two-sorted-arrays'><y>Find the intersection of two sorted arrays</y></h3>
#### <g>Example</g>
```javascript
  function intersection(arr1, arr2) {
  const result = [];
  let i = 0, j = 0;
  
  while (i < arr1.length && j < arr2.length) {
    if (arr1[i] === arr2[j]) {
      result.push(arr1[i]);
      i++;
      j++;
    } else if (arr1[i] < arr2[j]) {
      i++;
    } else {
      j++;
    }
  }
  
  return result;
}
```

[Back to Top](#table-of-contents)

### <h3 id='find-the-smallest-subarray-in-a-given-array-that-has-a-given-sum'><y>Find the smallest subarray in a given array that has a given sum</y></h3>
#### <g>Example</g>
```javascript
  function smallestSubarrayWithGivenSum(s, arr) {
  let windowSum = 0, minLength = Infinity;
  let windowStart = 0;
  
  for (let windowEnd = 0; windowEnd < arr.length; windowEnd++) {
    windowSum += arr[windowEnd]; // add the next element
    // shrink the window as small as possible until the 'windowSum' is smaller than 's'
    while (windowSum >= s) {
      minLength = Math.min(minLength, windowEnd - windowStart + 1);
      windowSum -= arr[windowStart]; // subtract the element going out
      windowStart++; // slide the window ahead
    }
  }
  return minLength === Infinity ? 0 : minLength;
}
```


### <h3 id='find-the-maximum-sum-of-a-subarray-of-a-given-array'><y>Find the maximum sum of a subarray of a given array</y></h3>
#### <g>Example</g>
```javascript
  function maxSubArraySum(arr) {
  let maxSum = 0;
  let currentSum = 0;
  
  for (let i = 0; i < arr.length; i++) {
    currentSum = Math.max(arr[i], currentSum + arr[i]);
    maxSum = Math.max(maxSum, currentSum);
  }
  
  return maxSum;
}
```

##### <b>**OR**</b>

```javascript
  function maxSubArraySum(arr) {
  let maxSum = 0;
  let currentSum = 0;
  
  for (let i = 0; i < arr.length; i++) {
    currentSum += arr[i];
    if (currentSum > maxSum) {
      maxSum = currentSum;
    }
    if (currentSum < 0) {
      currentSum = 0;
    }
  }
  
  return maxSum;
}
```

##### <b>**OR**</b>

```javascript
  function maxSubarraySum(arr) {
  let left = 0;
  let right = 0;
  let maxSum = -Infinity;
  let currentSum = 0;

  while (right < arr.length) {
    currentSum += arr[right];
    right++;

    while (currentSum > maxSum) {
      maxSum = currentSum;
    }

    while (currentSum < 0) {
      currentSum -= arr[left];
      left++;
    }
  }

  return maxSum;
}
```

[Back to Top](#table-of-contents)
