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

# <r>Binary Search</r>

## <o>The process of searching for a specific value in an ordered collection</o>

* Searching algorithm
* O(log n) time complexity

## <o>When to use</o>

* Any time you need to search for an index or element in a collection
* If the collection is unordered it can (and should) be sorted first
* Finding an elements position in a sorted array

## <o>Terminology for Binary Search</o>

* <h>**Target**</h> - The value you are searching for
* <h>**Index**</h> - The current location that you are searching
* <h>**Left, Right**</h> - The indicies from which we use to maintain our search Space
* <h>**Mid**</h> - The index we use to apply a condition to determine if we should search left or right

## <o>How it works</o>

1. The search target is compared to the middle value of the collection

  * This means it divides the search space in 2 after every comparison

2. If the condition is unsatisfied the half that cannot contain the target is eliminated

3. The search then continues on the remaining half

## <o>Templates for Binary Search</o>

### <y>Template #1</y>

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