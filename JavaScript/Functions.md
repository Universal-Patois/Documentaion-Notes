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
# <r>Reusable functions</r>

* Various functions that can be used for different purposes.

## <o>Table of Contents</o>

* [Format Number Function](#format-number-function)
* [Remove all non-alphanumeric characters from a string](#remove-all-non-alphanumeric-characters-from-a-string)

## <o>Format Number Function</o>

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

## <o>Remove all non-alphanumeric characters from a string</o>

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