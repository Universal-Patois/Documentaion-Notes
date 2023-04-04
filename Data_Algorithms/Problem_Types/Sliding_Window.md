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

# <r>Sliding Window</r>

* The sliding window uses one pointer and one variable for the window size to find a window within the sequence
* Used to check some subparts of a sequence
* We only need one pointer that shows the start of the subpart and an integer that indicates the size of the subpart(window)
* There are two variants to the sliding window technique:
    * Fixed window size
    * Variable window size
* Brings time complexity from O(n2) to O(n)

## <o>Fixed Window Size</o>

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

## <o>Flexible Window Size</o>

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
