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
# <h1 id='bigo-notation'><r>BigO Notation</r></h1>

* Algorithms are a set of instructions to solve a problem.
* Algorithmic thinking is the process of breaking down a problem into smaller problems.

## <o>Table of Contents</o>

* [<l>Time Complexity</l>](#time-complexity)
* [<l>Number of Operations</l>](#number-of-operations)
* [<l>Multiple Expressions<l>](#multiple-expressions)
* [<l>Space Complexity</l>](#space-complexity)
## <h2 id='time-complexity'><o>Time Complexity</o></h2>

*  Time complexity is the most important thing in algorithms. It is the most important thing to consider when you are designing, choosing and comparing an algorithm. How many primitive operations are performed by an algorithm?

 - <h>**Think**</h> - As our input size increases, how much time does it take to run an algorithm?

### <h2 id='number-of-operations'><y>Number of Operations</y></h2>

-  <i>**O(1)** (Fast) - *Constant Time*</i> is the fastest time complexity
    * It is the fastest. It only needs to access the first element in the array. The amount of time it takes to run an algorithm does not grow with the size of the input data set.
    * Number of operations: 2

      * <i>**example**</i>: Accessing the first element in an array is O(1). It only needs to access the first element in the array. If the array is 10 elements long, then 1 operation is performed O(1).

      * <i>**example**:</i> string.length - would be O(1) because JavaScript is storing the length of the string in memory. It is not looping through the string to get the length. It is accessing the length property.

* <i>**O(log n)** - *Logarithmic Time*</i> is the second best time complexity
  * It is faster than linear time, quadratic time, cubic time, and exponential time. It can have different bases. Base 10, Base 2. As your input increases the work(number of operations) decreases by a fraction. Time complexity grows very slow.

    * <i>**example**:</i> <h>*Binary search*</h> is O(log n) time complexity. If you have 100 elements, then you only need to perform 7 operations. Every time you loop you only need to work on half of the remaining elements.

- <i>**O(n)** - *Linear Time*</i> It only needs to loop through the input once
  * The amount of time it takes to run an algorithm grows at a rate of the size of the input data set.
  * Number of operations: 2n

    *  <i>**example**:</i> When comparing the minium and maximum values in an array, the value for max and minimum is stored and compared to the next value in the array. If the next value is greater than the max, then the max is updated. If the next value is less than the min, then the min is updated. 

    * <i>**example**:</i> <h>*shift*, *unshift*, *pop*, *push*</h> are all linear time operations. With shift and unshift, the array is shifted to the left or right and each element is moved to the next index. If the array is 10 elements long, then 10 operations are performed O(10).

* <i>**O(n^2)** (Slow) - *Quadratic Time*</i> is the worst time complexity. It is the slowest
  * It compares every element to every other element
  * The amount of time it takes to run an algorithm grows at a rate of the square of the size of the input data set.
  * Number of operations: n^2

[Back to top](#bigo-notation)

### <h2 id='multiple-expressions'><y>Multiple expressions</y></h2>

* <i>**O(1)**:</i> Running a statement, value lookup on an array, object, or variable.
* <i>**O(log n)**:</i> Loop that cuts the problem in half each time.
* <i>**O(n)**:</i> Loop that iterates through the values of an array once.
* <i>**O(n^2)**:</i> Nested loops(Double).
* <i>**O(n^3)**:</i> Nested loops(Triple).

## <h2 id='space-complexity'><o>Space Complexity</o></h2>

Space complexity is the amount of memory used by an algorithm.

### <y>Things to Consider</y>

 * Are you creating new data structures?
 * How often are you doing this in comparison to your input
 * <h>*Call stack*</h>- The call stack is taking place in memory. Something to consider with recursion.

[Back to top](#bigo-notation)
