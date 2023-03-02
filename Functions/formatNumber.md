# formatNumber function

```js
function formatNumber(num) {
  return num.toString().replace(/(\d)(?=(\d{3})+(?!\d))/g, '$1,');
}
```

## What it does

This code replaces every digit that is followed by groups of three digits (but not at the end of the number) with the same digit followed by a comma, effectively formatting the number with commas as thousands separators. 

## How it works

* The [toString()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toString) method is called on a number, converting it to a string. Then, the replace() method is used to match a regular expression pattern to add commas to the number.

* [replace()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace) is a string method that returns a new string with some or all matches of a pattern replaced by a replacement. The pattern can be a string or a RegExp, and the replacement can be a string or a function to be called for each match. If pattern is a string, only the first occurrence will be replaced.

* The regular expression pattern (\d)(?=(\d{3})+(?!\d)) is used to match any digit followed by groups of three digits, but not at the end of the number. The ?= symbol is a positive lookahead, meaning it matches the preceding expression without including it in the match result. The (?!d) is a negative lookahead which ensures the expression only matches up to the last group of digits, excluding any digits after that.

* The replacement string '$1,' inserts a comma after the matched digit. The $1 refers to the first capturing group in the pattern, which is the matched digit.

## Positive lookahead

See the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Assertions#positive_and_negative_lookahead_assertions) for more information on positive lookahead.

See notes in Regex section(Lookarounds) for more information on positive lookahead's.

## Negative lookahead

See the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Assertions#positive_and_negative_lookahead_assertions) for more information on negative lookahead.

See notes in Regex section(Lookarounds) for more information on negative lookahead's.