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

# <h1 id='regex'><r>Regex</r></h1>

## <h2 id='regex-1'><o>Example</o></h2>

```js
const str = "  Hello,  World!  ";
const trimmedStr = str.replace(/\s/g, "");
console.log(trimmedStr); // Output: "Hello,World!"
```

### <h3 id='breaking-it-down'><y>Breaking it down:</y></h3>
```/\s/g```: <b>Regular expression</b> that matches all whitespace characters in a string.


* <i>```/```</i>: <b>Delimiters</b> to indicate the start and end of the regular expression.

* <i>```\s```</i>: Represents the pattern to match. <i>```\s```</i> is a <b>special character class</b> that matches any whitespace character, including spaces, tabs, and line breaks.

* <i>```g```</i>: Global <b>flag</b>. When used with the regular expression, it ensures that all occurrences of the pattern are matched, rather than just the first occurrence.

#### <h4><g>Delimiter</g></h4>

* A delimiter in a regex expression is a character that marks the beginning or end of a section
* They are used to specify the start and end of a pattern
* In the example above, the delimiter is ```/```

#### <h4><g>Special Character Classes</g></h4>

* Special character classes are used to match a group of characters

| <i>Character Class</i> | <h>Description</h> |
| --- | --- |
| ```.``` | Matches any <hh>single character</hh> except line breaks (newline character ``\n``) |
| ```\w``` | Matches any <hh>word character</hh> (alphanumeric & underscore) <b>Equivalent to</b> ```[A-Za-z0-9_]``` |
| ```\W``` | Matches any <hh>non-word character</hh> (opposite of ```\w```) <b>Equivalent to</b> ```[^A-Za-z0-9_]``` |
| ```\d``` | Matches any <hh>digit character</hh> (0-9) <b>Equivalent to</b> ```[0-9]```|
| ```\D``` | Matches any <hh>non-digit character</hh> (opposite of ```\d```) <b>Equivalent to</b> ```[^0-9]``` |
| ```\s``` | Matches any <hh>whitespace character</hh> (space, tab, line break) <b>Equivalent to</b> ```[\t\n\f\r\p{Z}]``` |
| ```\S``` | Matches any <hh>non-whitespace character</hh>(opposite of ```\s```) <b>Equivalent to</b> ```[^\t\n\f\r\p{Z}]``` |
| ```\b``` | Matches a <hh>word boundary</hh> (the position between a word character and a non-word character). |
| ```\B``` | Matches a <hh>non-word boundary</hh> (opposite of ```\b```) |
| ```[]``` | Matches any <hh>character inside the square brackets</hh>. <b>For example</b> ```[aeiou]``` matches any vowel character.|
| ```[^]``` | Matches any <hh>character not inside the square brackets</hh>. <b>For example</b>, ```[^0-9]``` matches any non-digit character. |

##### <h5><b>Equivalent to Explained</b></h5>

* Above, we used ```[A-Za-z0-9_]``` to represent the word character class ```\w```
* We used ```[\t\n\f\r\p{Z}]``` to represent the whitespace character class ```\s```
* We used ```^``` to represent the negation of a character class

In ```[A-Za-z0-9_]```
| <i>Character Class</i> | <h>Description</h> |
| --- | --- |
| ```A-Z``` | Matches any <hh>uppercase letter</hh> from A to Z |
| ```a-z``` | Matches any <hh>lowercase letter</hh> from a to z |
| ```0-9``` | Matches any <hh>digit</hh> from 0 to 9 |
| ```_``` | Matches an <hh>underscore</hh> |

In ```[\t\n\f\r\p{Z}]```
| <i>Character Class</i> | <h>Description</h> |
| --- | --- |
| ```\t``` | Matches a <hh>tab</hh> |
| ```\n``` | Matches a <hh>line feed</hh> |
| ```\f``` | Matches a <hh>form feed</hh> |
| ```\r``` | Matches a <hh>carriage return</hh> |
| ```\p{Z}``` | Matches any <hh>Unicode separator character</hh> This is a <hh>Unicode property escape</hh> that matches any Unicode whitespace character. The ``\p{Z}`` syntax is used to match a character with a particular Unicode property. In this case, ``Z`` represents the property "Whitespace". The ``\p{Z}`` notation allows for matching various types of whitespace characters, including non-ASCII whitespace characters.|

* ``^``: Inside a character class, the caret symbol ``^`` at the beginning negates the character class. It indicates that the character class should match any character that is not included in the class.

#### <h4><g>Flags</g></h4>

* Flags are used to perform case-insensitive and global searches

| <i>Flag</i> | <h>Description</h> |  
| --- | --- |
| ```g``` | <hh>Global flag</hh>. When used, the regular expression matches all occurrences in the string, rather than just the first one.|
| ```i``` | <hh>Ignore case flag</hh>. When used, the regular expression performs a case-insensitive match. |
| ```m``` | <hh>Multiline flag</hh>. When used, the regular expression treats the beginning (``^``) and end (``$``) anchors as matching the start and end of each line, respectively, instead of just the start and end of the entire string.|
