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

# <h1 id="reusable-functions"><r>Reusable Functions</r></h1>

* Various functions that can be used for different purposes.

## <h2 id="table-of-contents"><o>Table of Contents</o></h2>

* [<l>Format Number Function</l>](#format-number-function)
* [<l>Remove All Non-alphanumeric Characters From a String</l>](#remove-all-non-alphanumeric-characters-from-a-string)
* [<l>Remove Duplicates From an Array</l>](#remove-duplicates-from-an-array)

## <h2 id="format-number-function"><o>Format Number Function</o></h2>

```js
function formatNumber(num) {
  return num.toString().replace(/(\d)(?=(\d{3})+(?!\d))/g, '$1,');
}
```

### <y>What it does</y>

This code replaces every digit that is followed by groups of three digits (but not at the end of the number) with the same digit followed by a comma, effectively formatting the number with commas as thousands separators. 

### <y>How it works</y>

* The [toString()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toString) method is called on a number, converting it to a string. Then, the replace() method is used to match a regular expression pattern to add commas to the number.

* [replace()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace) is a string method that returns a new string with some or all matches of a pattern replaced by a replacement. The pattern can be a string or a RegExp, and the replacement can be a string or a function to be called for each match. If pattern is a string, only the first occurrence will be replaced.

* The regular expression pattern (\d)(?=(\d{3})+(?!\d)) is used to match any digit followed by groups of three digits, but not at the end of the number. The ?= symbol is a positive lookahead, meaning it matches the preceding expression without including it in the match result. The (?!d) is a negative lookahead which ensures the expression only matches up to the last group of digits, excluding any digits after that.

* The replacement string '$1,' inserts a comma after the matched digit. The $1 refers to the first capturing group in the pattern, which is the matched digit.

### <y>Positive lookahead</y>

See the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Assertions#positive_and_negative_lookahead_assertions) for more information on positive lookahead.

See notes in Regex section [Lookarounds](../Regex/Lookarounds.md#positive-lookaheadlookbehind) for more information on positive lookahead's.

### <y>Negative lookahead</y>

See the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Assertions#positive_and_negative_lookahead_assertions) for more information on negative lookahead.

See notes in Regex section [Negative Lookarounds](../Regex/Lookarounds.md#negative-lookaheadlookbehind) for more information on negative lookahead's.

[Back to Top](#table-of-contents)

## <h2 id="remove-all-non-alphanumeric-characters-from-a-string"><o>Remove All Non-alphanumeric Characters From a String</o>

```javascript
const str = 'Hello, World!';
const newStr = str.replace(/[^a-z0-9]/gi, '');
```

### <y>Here is what each part of the code does</y>

* ```/[^a-zA-Z0-9]/gi```: This is a regular expression that matches any character that is not a letter or a digit (i.e., non-alphanumeric characters)
* The ``^`` symbol: Means that the pattern will match any character that is not in the set of characters specified
  * The ``^`` character inside a character class (enclosed in square brackets `[]`) is used to create a negated character class
  * Without the ``^`` symbol, the regular expression would match only the characters specified in the pattern
* The ``g`` flag: Means that the search is global (i.e., it will match all instances of the pattern, not just the first one)
* The ``i`` flag: Means case-insensitive (i.e., it will match both upper- and lowercase letters)
  * Without the ``i`` flag, the regular expression would only match the exact case of the letters specified in the pattern
* ``''``: This is the replacement string that will replace any matches found by the regular expression. In this case, it is an empty string, effectively removing any non-alphanumeric characters from the string.


## <o>Checking if a number is even or odd</o>

```javascript
function isEven(num) {
  return num % 2 === 0;
}
```

* The `%` symbol is the modulus operator, which gives you the remainder of the division between `num` and `2`
* If `num` is an even number, the remainder of num divided by `2` will always be `0`

[Back to Top](#table-of-contents)

## <h2 id="remove-duplicates-from-an-array"><o>Remove Duplicates From an Array</o>
* This can be attempted with a [two pointer approach](../Data_Algorithms/Problem_Types/Two_Pointer.md). But can also be done with a set and spread operator or filter method.

### <y>Set and Spread Operator</y>
* The Set constructor creates a new Set object. A Set is a collection of values, where each value may occur only once.
* Here the set is used to remove duplicates from the array.
* The numbers are spliced from the array parameter and replaced with the spread operator of the set.

#### <g>Example</g>
```javascript
function removeDuplicates(nums: number[]): number {
    const withoutDuplicates = new Set(nums)
    nums.splice(0, nums.length, ...withoutDuplicates)
    return nums
```

### <y>Filter Method</y>
* The filter() method creates a new array with all elements that pass the test implemented by the provided function.
* Here the filter method uses a callback function to check if the index of the current element is equal to the first index of the element in the array.

#### <g>Example</g>
```javascript
function removeDuplicates(nums: number[]): number {
    return nums.filter((num, index) => nums.indexOf(num) === index)
}
```

### <y>While Loop</y>
* The while loop is used to iterate through the array and check if the current element is equal to the next element.
* If it is, the current element is spliced from the array.
* If it is not, the index is incremented.

#### <g>Example</g>
```javascript
function removeDuplicates(nums: number[]): number {
    if (nums.length === 0) return 0;
    if (nums.length === 1) return 1;

      let i = 0;
    while (i < nums.length) {
        let j = i + 1;
        while (j < nums.length) {
            if (nums[i] === nums[j]) {
                nums.splice(j, 1); // Remove duplicate element at index j
            } else {
                j++;
            }
        }
        i++;
    }
    return nums.length;
}
```

[Back to Top](#table-of-contents)