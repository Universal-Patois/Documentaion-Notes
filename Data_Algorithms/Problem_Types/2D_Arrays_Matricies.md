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

<h1 id="2D_Arrays_Matrices"><r>2D Arrays/Matrices</r></h1>

* A 2D array is a collection of data elements organized in a 2D grid
* Each element in a 2D array is uniquely identified by its row and column index *(or coordinates)* (ex. `array[row][column]`)
* In JavaScript, there is no direct syntax for creating 2D arrays as with other commonly used programming languages like C, C++, and Java.

## <h2 id="table-of-contents"><o>Table of Contents</o></h2>
* [<l>When to use</l>](#when-to-use)
* [<l>How to use</l>](#how-to-use)
* [<l>Example</l>](#example)

## <h2 id="when-to-use"><o>When to use</o></h2>

They allow for the efficient storage and manipulation of large amounts of data, such as in image or video processing, scientific simulations, and spreadsheet applications.

1. <y>Image Processing</y>
  * In image processing, matrices are used to represent images. Diagonal sums might be relevant in certain image analysis algorithms or feature extraction techniques.
2. <y>Computer Graphics</y>
  * In computer graphics, matrices are used to project 3D points onto a 2D screen. The inverse of the projection matrix can be used to convert 2D points on the screen to 3D points in the world.
  * Matrices are extensively used in computer graphics. Diagonal differences could be involved in algorithms related to image transformation or manipulation.
3. <y>Scientific Computing</y>
  * In scientific simulations and computations, matrices often represent physical systems. Diagonal differences could have applications in analyzing simulation results.

## <h2 id="how-to-use"><o>How to use</o></h2>

### <h3 id="creating-a-2d-array"><y>Creating a 2D Array</y></h3>

You can create two-dimensional arrays in JavaScript through jagged arrays — an array of arrays
* Two dimensional arrays have a fixed size, meaning once they are created the number of rows and columns should be fixed
* You don't get to specify a fixed row and column. Meaning you can have a 2D array could have m rows, each having a different number of elements (columns)

#### <g>Example</g>

##### <b>Array Literal Notation</b>
```javascript
let twoDimensionalArr = [ 
[ a1, a2, a3, ..., an ],
[ b1, b2, b3, ..., bn ],
[ c1, c2, c3, ..., cn ]
];
```
* This uses square brackets to wrap a list of elements separated by commas

##### <b>Nested Loops</b>
```javascript
let arr = [];
let rows = 4;
let columns = 3;

// creating two-dimensional array
for (let i = 0; i < rows; i++) {
  arr[i] = [];
  for (let j = 0; j < columns; j++) {
    arr[i][j] = j;
  }
}

console.log(arr);
let arr = [
  [0, 1, 2],
  [0, 1, 2],
  [0, 1, 2],
  [0, 1, 2]
]
```
* Generally, you create a nested loop where the first loop will loop through the rows
* While the second loop will loop through the elements in the inner array (columns)

##### <b>Array map()</b>
```javascript
let arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
let matrix = arr.map((row => row.split(' ').map(Number)));

console.log(matrix);
let matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];
```



### <h3 id="accessing-elements-in-a-2d-array"><y>Accessing Elements in a 2D Array</y></h3>

You can access elements in a 2D array by specifying the row and column index of the element
* ```arrayName[rowIndex][columnIndex]```

* To better visualize this, convert the two-dimensional array to a table using ``console.table(arrayName)``

#### <g>Accessing the First or Last Element in a 2D Array</g>

* The first element will always be at `arrayName[0][0]`


## <h2 id="example"><o>Example</o></h3>

Given a square matrix, calculate the absolute difference between the sums of its diagonals.

```javascript
function diagonalDifference(arr) {
  // Step 1: Create the Matrix
  const n = arr.length;

  // If the arr is an array of string numbers.
  // If not this step can be skipped
  const matrix = arr.map(row => row.split(' ').map(Number));

  // Step 2: Calculate Diagonal Sums
  let leftToRightSum = 0;
  let rightToLeftSum = 0;

  for (let i = 0; i < n; i++) {
    leftToRightSum += matrix[i][i];
    rightToLeftSum += matrix[i][n - 1 - i];
  }

  // Step 3: Calculate Absolute Difference
  const absoluteDifference = Math.abs(leftToRightSum - rightToLeftSum);

  // Return the result
  return absoluteDifference;
}

// Example Usage:
const inputArray = [
  "1 2 3",
  "4 5 6",
  "9 8 9"
];

const result = diagonalDifference(inputArray);
console.log(result); // Output: 2
```

1. <g>Left-to-Right Diagonal Sum</g>
    * `matrix[i][i]` refers to the element at the ith row and ith column of the matrix.
    * In the context of the left-to-right diagonal, `i` represents both the row and column index
    * You are summing the elements along the diagonal from the top-left corner to the bottom-right corner.
    * This line accumulates the sum of the left-to-right diagonal as you iterate through the rows.

2. <g>Right-to-Left Diagonal Sum</g>
    * `matrix[i][n - 1 - i]` refers to the element at the ith row and (n - 1 - i)th column of the matrix.
    * In the context of the right-to-left diagonal, `i` represents the row index, while `(n - 1 - i)` represents the column index.
    * You are summing the elements along the diagonal from the top-right corner to the bottom-left corner.


## <h2 id="resources"><o>Resources</o></h2>
[FreeCodeCamp - 2D Arrays](https://www.freecodecamp.org/news/2d-arrays-in-javascript/)