# [Lookaround's](https://www.regular-expressions.info/lookaround.html)

## [Assertions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Assertions#positive_and_negative_lookahead_assertions)

## Positive Lookahead/lookbehind

A positive lookahead will look to make sure the element in the search pattern is there, but won't actually match it. A positive lookahead is written as `(?=...)`.

## How it works

### Lookahead
**Lookahead After the Match**: ```\d+(?= dollars)```
**Sample Match**: 100 in 100 dollars
**Explanation**: ```\d+``` matches the digits 100, then the lookahead ``(?= dollars)`` asserts that at that position in the string, what immediately follows is the characters " dollars"

**Lookahead Before the Match**: ```(?=\d+ dollars)\d+```
**Sample Match**: 100 in 100 dollars
**Explanation**: The lookahead ```(?=\d+ dollars)``` asserts that at the current position in the string, what follows is digits then the characters " dollars". If the assertion succeeds, the engine matches the digits with ```\d+```.

### Lookbehind
**Lookbehind Before the match**: ``(?<=USD)\d{3}``
**Sample Match**: 100 in USD100
**Explanation**: The lookbehind ```(?<=USD)``` asserts that at the current position in the string, what precedes is the characters "USD". If the assertion succeeds, the engine matches three digits with ```\d{3}```.

**Lookbehind After the match**: ``\d{3}(?<=USD\d{3})``
**Sample Match**: 100 in USD100
**Explanation**: ```\d{3}``` matches the digits 100, then the lookbehind ```(?<=USD)\d{3}``` asserts that at that position in the string, what immediately precedes is the characters "USD"

## Negative Lookahead/lookbehind

A negative lookahead will look to make sure the element in the search pattern is not there. A negative lookahead is written as `(?!...)`.

## How it works

### Negative Lookahead
**Negative Lookahead After the Match**: ```\d+(?!\d| dollars)```
**Sample Match**: 100 in 100 dollars
**Explanation**: ```\d+``` matches the digits 100, then the negative lookahead ```(?!\d| dollars)``` asserts that at that position in the string, what immediately follows is neither a digit nor the characters " dollars"

**Negative Lookahead Before the Match**: ```(?!\d+ dollars)\d+```
**Sample Match**: 100 in 100 dollars
**Explanation**: The negative lookahead ```(?!\d+ dollars)``` asserts that at the current position in the string, what follows is not digits then the characters " dollars". If the assertion succeeds, the engine matches the digits with ```\d+```.

### Negative Lookbehind

**Negative Lookbehind Before the match**: ``(?<!USD)\d{3}``
**Sample Match**: 100 in USD100
**Explanation**: The negative lookbehind ```(?<!USD)``` asserts that at the current position in the string, what precedes is not the characters "USD". If the assertion succeeds, the engine matches three digits with ```\d{3}```.

**Negative Lookbehind After the match**: ``\d{3}(?<!USD\d{3})``
**Sample Match**: 100 in USD100
**Explanation**: ```\d{3}``` matches the digits 100, then the negative lookbehind ```(?<!USD)\d{3}``` asserts that at that position in the string, what immediately precedes is not the characters "USD"