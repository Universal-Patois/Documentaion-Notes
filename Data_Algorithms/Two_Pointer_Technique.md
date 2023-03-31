# Two Pointer technique

* Two pointer problems are a type of problem where you have a list of elements and you need to find a pair of elements that satisfy a certain condition.
* These problems usually involve two pointers, one slow-runner and one fast-runner.

## Table of Contents

* [When to use](#when-to-use)
* | **[Types of Two Pointer Techniques](#types-of-two-pointer-techniques)** |
  | --------------------------------- |
  | - *[Two Pointers Approach](#two-pointers-approach)* |
  | - *[Sliding Window Technique](#sliding-window-technique)* |
  | - *[Two Pointers with Hash Table](#two-pointers-with-hash-table)* |
* | **[Types of Two Pointer Problems](#types-of-two-pointer-problems)** |
  | --------------------------------- |
  | - *[Searching for a pair of elements in a sorted array](#searching-for-a-pair-of-elements-in-a-sorted-array)* |
  | - *[Remove Duplicates from Sorted Array](#remove-duplicates-from-sorted-array)* |
  | - *[Check if a string is a palindrome](#check-if-a-string-is-a-palindrome)* |
  | - *[Find the longest substring that is a palindrome](#find-the-longest-substring-that-is-a-palindrome)* |
  | - *[Find the intersection of two sorted arrays](#find-the-intersection-of-two-sorted-arrays)* |
  | - *[Find the smallest subarray in a given array that has a given sum](#find-the-smallest-subarray-in-a-given-array-that-has-a-given-sum)* |
  | - *[Find the maximum sum of a subarray of a given array](#find-the-maximum-sum-of-a-subarray-of-a-given-array)* |
## When to use

The two pointer technique is a useful and versatile algorithmic pattern that can be applied to a wide range of problems, particularly those involving ```arrays``` and ```linked lists```

* Searching for a pair of elements in a sorted array
* Removing duplicates from a sorted array
* Checking whether a given string is a palindrome
* Finding the longest substring that is a palindrome
* Finding the intersection of two sorted arrays
* Finding the smallest subarray in a given array that has a given sum
* Finding the maximum sum of a subarray of a given array

[Back to top](#table-of-contents)
## Types of Two Pointer Techniques

### Two Pointers Approach

* **Usually starting from the beginning and end of an array or list, and moving them towards each other until they meet**
* It is often used to solve problems related to **searching or sorting**
* Can be used to reduce the time complexity of an algorithm from O(n^2) to O(n)

#### Example

* Given an array of integers and a target sum, find a pair of numbers in the array that add up to the target sum

### Sliding Window Technique

* **Usually starting at the beginning of an array or list, and moving one or both of them in a specific direction to create a window or subarray**
* It is often used to solve problems related to **substring or subarray manipulation**
* Can be used to reduce the time complexity of an algorithm from O(n^2) to O(n)

#### Example

* Given a string and a pattern, find the smallest substring in the string that contains all the characters in the pattern

### Two Pointers with Hash Table

* This technique involves using two pointers and a hash table to efficiently solve problems that require **tracking the occurrence or frequency of elements in an array or list**
* It is often used to reduce the time complexity of an algorithm from O(n^2) to O(n).

#### Example

* Given an array of integers and a target sum, find all pairs of numbers in the array that add up to the target sum

[Back to top](#table-of-contents)
## Types of Two Pointer Problems

### Searching for a pair of elements in a sorted array
#### Example

```javascript

```
### Remove Duplicates from Sorted Array
#### Example

```javascript

```
### Check if a string is a palindrome
#### Example

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

### Find the longest substring that is a palindrome
#### Example

```javascript

```

### Find the intersection of two sorted arrays
#### Example

```javascript

```

### Find the smallest subarray in a given array that has a given sum
#### Example

```javascript

```

### Find the maximum sum of a subarray of a given array
#### Example

```javascript

```

[Back to top](#table-of-contents)
