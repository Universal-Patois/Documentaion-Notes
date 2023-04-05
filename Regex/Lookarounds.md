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

# <r>Lookarounds</r>

* [Lookaround's](https://www.regular-expressions.info/lookaround.html)
* [Assertions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Assertions#positive_and_negative_lookahead_assertions)

## <o>Positive Lookahead/lookbehind</o>

A positive lookahead will look to make sure the element in the search pattern is there, but won't actually match it. A positive lookahead is written as `(?=...)`.

### <y>How it works</y>

#### <g>Lookahead</g>

##### <b>**Lookahead After the Match**</b>: ```\d+(?= dollars)```
* <i>**Sample Match**</i>: 100 in 100 dollars
* <h>**Explanation**</h>: ```\d+``` matches the digits 100, then the lookahead ``(?= dollars)`` asserts that at that position in the string, what immediately follows is the characters " dollars"

##### <b>**Lookahead Before the Match**</b>: ```(?=\d+ dollars)\d+```
* <i>**Sample Match**</i>: 100 in 100 dollars
* <h>**Explanation**</h>: The lookahead ```(?=\d+ dollars)``` asserts that at the current position in the string, what follows is digits then the characters " dollars". If the assertion succeeds, the engine matches the digits with ```\d+```.

#### <g>Lookbehind</g>
##### <b>**Lookbehind Before the match**</b>: ``(?<=USD)\d{3}``
* <i>**Sample Match**</i>: 100 in USD100
* <h>**Explanation**</h>: The lookbehind ```(?<=USD)``` asserts that at the current position in the string, what precedes is the characters "USD". If the assertion succeeds, the engine matches three digits with ```\d{3}```.

##### <b>**Lookbehind After the match**</b>: ``\d{3}(?<=USD\d{3})``
* <i>**Sample Match**</i>: 100 in USD100
* <h>**Explanation**</h>: ```\d{3}``` matches the digits 100, then the lookbehind ```(?<=USD)\d{3}``` asserts that at that position in the string, what immediately precedes is the characters "USD"

## <o>Negative Lookahead/lookbehind</o>

A negative lookahead will look to make sure the element in the search pattern is not there. A negative lookahead is written as `(?!...)`.

### <y>How it works</y>

#### <g>Negative Lookahead</g>
##### <b>**Negative Lookahead After the Match**</b>: ```\d+(?!\d| dollars)```
* <i>**Sample Match**</i>: 100 in 100 dollars
* <h>**Explanation**</h>: ```\d+``` matches the digits 100, then the negative lookahead ```(?!\d| dollars)``` asserts that at that position in the string, what immediately follows is neither a digit nor the characters " dollars"

##### <b>**Negative Lookahead Before the Match**</b>: ```(?!\d+ dollars)\d+```
* <i>**Sample Match**</i>: 100 in 100 dollars
* <h>**Explanation**</h>: The negative lookahead ```(?!\d+ dollars)``` asserts that at the current position in the string, what follows is not digits then the characters " dollars". If the assertion succeeds, the engine matches the digits with ```\d+```.

#### <g>Negative Lookbehind</g>

##### <b>**Negative Lookbehind Before the match**</b>: ``(?<!USD)\d{3}``
* <i>**Sample Match**</i>: 100 in USD100
* <h>**Explanation**</h>: The negative lookbehind ```(?<!USD)``` asserts that at the current position in the string, what precedes is not the characters "USD". If the assertion succeeds, the engine matches three digits with ```\d{3}```.

##### <b>**Negative Lookbehind After the match**</b>: ``\d{3}(?<!USD\d{3})``
* <i>**Sample Match**</i>: 100 in USD100
* <h>**Explanation**</h>: ```\d{3}``` matches the digits 100, then the negative lookbehind ```(?<!USD)\d{3}``` asserts that at that position in the string, what immediately precedes is not the characters "USD"