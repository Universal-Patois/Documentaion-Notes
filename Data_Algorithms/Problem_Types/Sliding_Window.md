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

# <h1 id='sliding-window'><r>Sliding Window</r></h1>
* The sliding window uses one pointer and one variable for the window size to find a window within the sequence
* We only need one pointer that shows the start of the subpart and an integer that indicates the size of the subpart(window)
* There are two variants to the sliding window technique:
    * Fixed window size
    * Variable window size
* Brings time complexity from O(n2) to O(n)
## <o>Table of Contents</o>

* [<l>When to Use</l>](#when-to-use)
* [<l>Drawbacks</l>](#drawbacks)
* [<l>How to Use</l>](#how-to-use)
* [<l>Fixed Window Size</l>](#fixed-window-size)
* [<l>Flexible Window Size</l>](#flexible-window-size)

## <h2 id='when-to-use'><o>When to Use</o></h2>

### <y>Problems they are good for solving</y>
* Problems that involve sequential data (strings, arrays, linked lists)
* To efficiently process a fixed size subpart of a sequence of elements within a larger array or sequence
* Finding the maximum sum of a subarray of a fixed size
* Counting the number of subarrays that satisfy a certain condition
* Finding the smallest subarray that contains all the elements of a given set
* When the problem requires considering consecutive elements of a sequence or array, and the solution depends on the order of the elements
### <y>Most commonly seen in</y>
* Applications where the data is sequential and the order of the elements is important, such as in <h>time series analysis</h> or <h>sequence alignment</h>
## <h2 id='drawbacks'><o>Drawbacks</o></h2>
* It may not always be possible to find an optimal solution using the sliding window technique
  * The solution may depend on elements outside the current window
* Choosing an appropriate window size can be a challenging task
  * It may depend on the specific problem being solved and the characteristics of the input data

### <y>Advantages</y>
* It is efficient
* It avoids unnecessary computations by only examining a subset of the elements at each step
* It is easy to implement
* Can often provide and optimal or near-optimal solution

[Back to Top](#sliding-window)
## <h2 id='how-to-use'><o>How to Use</o></h2>
* The sliding window technique involves defining a window of a fixed size that slides over the sequence or array
* At each step, the elements within the window are examined to determine if they satisfy the condition
* By sliding the window over the sequence or array, all possible sub-sequences or subsets are considered, and the optimal solution is obtained.

### <y>Example</y>
1. <i>**Define the problem and the input sequence**</i>
    * Before applying the technique, we need to define the problem  we want to solve and the input sequence to analyze
2. <i>**Define the window size**</i>
    * The window size is the number of elements that are considered at each step
    * The window size can be fixed or variable
3. <i>**Initialize the window and calculate the initial result**</i>
    * Initialize the window to start at the first element of the input sequence
    * Calculate the initial result by examining(summing) the elements within the window
4. <i>**Slide the window and update the result**</i>
    * Slide the window over the sequence or array by one element at a time
    * At each step, update the result by removing the element that is no longer in the window and adding the new element that is now in the window
    * Repeat steps 3 and 4 until the end of the sequence or array is reached
5. <i>**Keep track of the maximum result**</i>
    * Keep track of the maximum result seen so far
    * The maximum result is the solution to the problem
6. <i>**Return the maximum result**</i>
    * After the sliding process is complete, return the maximum result

[Back to Top](#sliding-window)
## <h2 id='fixed-window-size'><o>Fixed Window Size</o></h2>
* We need two logics for this
    * <h>*First*</h> is when to update the size of the window
    * <h>*Second*</h> is when to update the pointer to a new location

### <y>Example</y>
* Find the max sum of K consecutive elements in an array (window size K is fixed)

1. Check that the array is larger than the expected window size, or we return null
2. Create first window with the first K number
3. Iterate through the array starting from the Kth element
    * If the current sum is greater than the max sum, set the max sum to the current sum
4. Return the max value

```javascript
function maxSum(arr, k) {
  if (k > arr.length) {
    return null;
  }

  let maxSum = 0;

  for (let i = 0; i < k; i++) {
    maxSum += arr[i];
  }

  let currentSum = maxSum;

  for (let i = k; i < arr.length; i++) {
    currentSum += arr[i] - arr[i - k];
    maxSum = Math.max(maxSum, currentSum);
  }

  return maxSum;
}

// Example usage:
const arr = [1, 3, 2, 6, 2, 1, 4, 5];
const k = 3;
const result = maxSum(arr, k); // returns 12
```

[Back to Top](#sliding-window)
## <h2 id='flexible-window-size'><o>Flexible Window Size</o></h2>
* The main idea is that at each run of the loop we add a new element and remove one

### <y>Example</y>
* Find the max sum of consecutive integers within the array” (There is no size limit K for the window, and it can have negative numbers).

1. Check the array is not empty or we sent 0 as the max sum
2. Declare two variables, max sum and current sum(set with 0)
3. Iterate through each number in the array
    * If the current number is positive: there are two options
        1. If the current sum is negative, we replace the current sum wit the current
        2. If the current sum is positive, we add the current number to the current sum
4. Then we check if the current sum is greater than the max sum; if so, we replace if
5. Eventually, we return the max sum

```javascript

function maxContiguousSum(numbers) {
  if (arr.length <= 0) return 0

  let maxSum = 0;
  let currentSum = 0;

  for (num in numbers ) {
    if( num >= 0) {
      currentSum = currentSum < 0 ? num : currentSum + num
    } else if (currentSum > maxSum) {
      maxSum = currentSum
    } else {
      currentSum += num
    }
  }
  return maxSum;
}
```

[Back to Top](#sliding-window)