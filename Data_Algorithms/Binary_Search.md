# [Binary Search](https://leetcode.com/problems/binary-search/solutions/2794222/binary-search/)

## The process of searching for a specific value in an ordered collection

* O(log n) time complexity

## When to use

* Any time you need to search for an index or element in a collection
* If the collection is unordered it can (and should) be sorted first

## Terminology for Binary Search

* **Target** - The value you are searching for
* **Index** - The current location that you are searching
* **Left, Right** - The indicies from which we use to maintain our search Space
* **Mid** - The index we use to apply a condition to determine if we should search left or right

## How it works

1. The search target is compared to the middle value of the collection

  * This means it divides the search space in 2 after every comparison

2. If the condition is unsatisfied the half that cannot contain the target is eliminated

3. The search then continues on the remaining half

## Templates for Binary Search

### Template #1

```javascript
const calcMid = (left, right) => {
    return left + Math.floor((right - left) / 2);
}

var search = function(numbers, target) {
    let left = 0;
    let right = numbers.length - 1;
    
    while (right >= left) {
        const mid = calcMid(left, right);
   
        if (numbers[mid] == target) {
            return mid;  
        } else if (numbers[mid] > target) {
            right = mid - 1;
        } else {
            left = mid + 1;
        }
    }

    return -1;
};
```

## [More on Binary Search](https://leetcode.com/explore/learn/card/binary-search/126/template-ii/)