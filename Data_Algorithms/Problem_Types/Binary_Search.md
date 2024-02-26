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
* [<l>Considerations</l>](#considerations)

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
    * If the target value is less than the middle element, set the right index to the middle index minus 1
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

## <h2 id='considerations'><o>Considerations</o></h2>

### <y>Problems That Can Occur</y>

* Infinity loops
* Can't decide where to shrink the search space
* Do I use Low(Left) or High(Right) 
* When to exit the loop

It may seem like binary search is such a simple idea, but when you look closely in the code, we are making some serious decisions that can completely change the behavior of our code.
These decisions include:

1. Do I use Low(Left) or High(Right) ``mid``?
2. Do I use ``>`` or ``>=``, ``<`` or ``<=``?
3. How much do I shrink the boundary? Is it ``mid`` or ``mid - 1`` or even ``mid + 1``?

### <y>How to Avoid These Problems</y>

To solve these decision problems, use the following set of rules to always keep away from trouble

#### <g> 1. Choice of ``low(left)`` or ``high(right), aka the boundary``</g>
Normally, we set the initial boundary to the number of elements in the array

```javascript
let low = 0
let high = nums.length - 1;
```

But this is not always the case.
* <hh>We need to remember</hh>: <l>**the boundary is the range of elements we will be searching from.**</l>
* The initial boundary should include **ALL** the elements, meaning all the possible answers should be included
* Binary search can be applied to none array problems, such as Math, and this statement is still valid.

##### <b>For example</b>
In LeetCode 35, the question asks us to find an index to insert into the array.
It is possible that we insert after the last element of the array, thus the complete range of boundary becomes
```let lo = 0, hi = nums.length;```

#### <g> 2. Calculate ``mid``</g>
Calculating mid can result in overflow when the numbers are extremely big.

```javascript
let mid = Math.floor((lo + hi) / 2) // worst, very easy to overflow

let mid = lo + Math.floor((hi - lo) / 2) // much better, but still possible

let mid = (lo + hi) >>> 1 // the best, but hard to understand
```

* When we are dealing with even elements, it is our choice to pick the left ``mid`` or the right ``mid``, and a bad choice will lead to an infinity loop.

```javascript
let mid = lo + Math.floor((hi - lo) / 2) // left/lower mid

let mid = lo + Math.floor((hi - lo + 1) / 2) // right/upper mid
```

#### <g> 3. Shrink the boundary</g>
 Try to keep the logic as simple as possible. As well, try to use a logic that <l>excludes</l> ``mid``

```javascript
if (target < nums[mid]) {
	hi = mid - 1
} else {
	lo = mid; 
}
```

Here, if the target is less than mid, there's no way mid will be our answer, and we can exclude it very confidently using hi = mid - 1. Otherwise, mid still has the potential to be the target, thus we include it in the boundary lo = mid.
On the other hand, we can rewrite the logic as:

```javascript
if (target > nums[mid]) {
	lo = mid + 1; // mid is excluded
} else {
	hi = mid; // mid is included
}
```

#### <g>Avoiding Infinity Loops</g>
A bad choice of left or right ``mid`` will lead to an infinity loop. 

##### <b>Example</b>
```javascript
let mid = lo + ((hi - lo) / 2); // Bad! We should use right/upper mid!

if (target < nums[mid]) {
	hi = mid - 1
} else {
	lo = mid; 
}
```
Now, imagine when there are only 2 elements left in the boundary
* If the logic fell into the else statement, since we are using the left/lower mid, it's simply not doing anything
* It just keeps shrinking itself to itself, and the program got stuck.
We have to keep in mind that, the choice of mid and our shrinking logic has to work together in a way that every time, at least 1 element is excluded.

##### <b>Example</b>
```javascript
let mid = lo + ((hi - lo + 1) / 2); // Bad! We should use left/lower mid!

if (target > nums[mid]) {
	lo = mid + 1; // mid is excluded
} else {
	hi = mid; // mid is included
}
```

So when your binary search is stuck, think of the situation when there are only 2 elements left. Did the boundary shrink correctly?


[Back to Top](#table-of-contents)