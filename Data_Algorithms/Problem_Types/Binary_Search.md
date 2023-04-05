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

# <h1 id='binary-search'><r>Binary Search</r></h1>
* Is a search algorithm that finds the position of a target value within a sorted array
* It is a divide and conquer algorithm that repeatedly splits the search space in half
* Its time complexity is O(log n)

## <h2 id='table-of-contents'><o>Table of Contents</o></h2>
* [<l>When to use</l>](#when-to-use)
* [<l>Drawbacks</l>](#drawbacks)
* [<l>How to use</l>](#how-to-use)
* [<l>Terminology</l>](#terminology)
* [<l>Examples</l>](#examples)

## <h2 id='when-to-use'><o>When to Use</o></h2>
* When you need to find an element in a sorted array or list
### <y>Problems they are good for solving</y>
* Searching for an index or element in a collection (array, linked list, etc.)
* Finding an elements position in a sorted array

### <y>Most commonly seen in</y>
* Situations where fast searching times are critical and the dataset is large and sorted

## <h2 id='drawbacks'><o>Drawbacks</o></h2>
* The array or list must be sorted before the search can be performed
* It may not be the best option for small datasets
    * The overhead of the algorithm may outweigh the benefits of its efficiency
* It requires random access to the data which may not be available in some situations

### <y>Advantages</y>
* It is a lot faster than linear search's O(n) time complexity
* It is very efficient for large arrays or lists
* It works well for both static and dynamic datasets
* It is a relatively simple algorithm to implement

[Back to Top](#table-of-contents)

## <h2 id='how-to-use'><o>How to Use</o></h2>
* The key idea is to compare the search key with the middle element of the array or list
* If the key is less than the middle element, the search continues in the lower half of the array or list
* This process is repeated until the key is found or the search space is exhausted

##### <y>**THE ARRAY/LIST MUST BE SORTED FIRST**</y>
1. <i>Determine the search range</i>
    * The search range is the range of indices that you are searching
    * The search range is initially the entire array or list
2. <i>Calculate the middle index</i>
    * Add the first and last indices together andd divide by 2
3. <i>Compare the target value to the middle element</i>
    * If the target value is equal to the middle element, return the middle index
    * If the target value is less than the middle element, set the last index to the middle index minus 1
    * If the target value is greater than the middle element, set the first index to the middle index plus 1
4. <i>Repeat steps 2 and 3 until the target value is found or the search range is exhausted</i>
## <h2 id='terminology'><o>Terminology for Binary Search</o></h2>
* <h>**Target**</h> - The value you are searching for
* <h>**Index**</h> - The current location that you are searching
* <h>**Left, Right**</h> - The indices from which we use to maintain our search Space
* <h>**Mid**</h> - The index we use to apply a condition to determine if we should search left or right

[Back to Top](#table-of-contents)
## <h2 id='examples'><o>Example for Binary Search</o></h2>
* Find the index of a specific integer in the array
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
##### [More on Binary Search](https://leetcode.com/explore/learn/card/binary-search/126/template-ii/)

[Back to Top](#table-of-contents)