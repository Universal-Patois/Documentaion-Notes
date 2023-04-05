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

# <r>Notes</r>

## <o>Table of Contents</o>

* [Comparison Operators](#comparison-operators)
* [Escape Sequences](#escape-sequences)
## <o>Comparison Operators</o>
In JavaScript, the comparison operators above can also be used to compare strings.
In that case, a dictionary (lexicographical) order is applied.
You can find a list of the exact order of all the characters [here][utf-16-list].

```javascript
'Apple' > 'Pear';
// => false

'a' < 'above';
// => true

'a' === 'A';
// => false
```

## <o>Escape Sequences</o>

In JavaScript, there are some special characters that are not allowed in strings.
For example, the double quote (`"`) is used to mark the beginning and end of a string.
If you want to include a double quote in a string, you need to escape it with a backslash (`\`).

To accomplish these tasks with little hassle you begin with a backslash ( \ ) within the string, which in essence tells the compiler “Stop! The upcoming text is special.”

### <y>Types of Escape Sequences</y>

There are two types of escape sequences: single-character escape sequences and Unicode escape sequences. The single-character escape sequences are listed below: 

| <h>Escape Sequence</h> | <h>Description<h/> |
| --- | --- |
| <hh>\0</hh> | Null character |
| <hh>\b</hh> | Backspace |
| <hh>\f</hh> | Form feed |
| <hh>\n</hh> | New line |
| <hh>\r</hh> | Carriage return |
| <hh>\t</hh> | Horizontal tab |
| <hh>\'</hh> | Single quote |
| <hh>\"</hh> | Double quote |
| <hh>\\</hh> | Backslash |
| <hh>\a</hh> | Alert (bell) |
| <hh>\s</hh> | Space |

### <y>What Each Escape Sequence Does</y>

The following table shows the escape sequences and what they do:

* <h>***Null character***</h>: The null escape sequence adds a null character to the string. This is a character with no value. It is used to terminate a string. It is not visible in the output.

* <h>***Backspace***</h>: The backspace escape sequence moves the cursor back one space. It is used to overwrite the previous character.

* <h>***Form feed***</h>: The form feed escape sequence moves the cursor to the beginning of the next page. It is used to start a new page.

* <h>***New line***</h>: The new line escape sequence moves the cursor to the beginning of the next line. It is used to start a new line.

* <h>***Carriage return***</h>: The carriage return escape sequence moves the cursor to the beginning of the current line.

* <h>***Horizontal tab***</h>: The horizontal tab escape sequence moves the cursor a couple of spaces to the right in the same line.

* <h>***Single quote***</h>: The single quote escape sequence adds a single quote to the string.

* <h>***Double quote***</h>: The double quote escape sequence adds a double quote to the string.

* <h>***Backslash***</h>: The backslash escape sequence adds a backslash to the string.

* <h>***Alert (bell)***</h>: The alert escape sequence makes a sound. It is used to alert the user of something.

* <h>***Space***</h>: The space escape sequence adds a space to the string.

