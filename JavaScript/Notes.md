## Comparison Operators
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

## Escape Sequences

In JavaScript, there are some special characters that are not allowed in strings.
For example, the double quote (`"`) is used to mark the beginning and end of a string.
If you want to include a double quote in a string, you need to escape it with a backslash (`\`).

To accomplish these tasks with little hassle you begin with a backslash ( \ ) within the string, which in essence tells the compiler “Stop! The upcoming text is special.”

### Types of Escape Sequences

There are two types of escape sequences: single-character escape sequences and Unicode escape sequences. The single-character escape sequences are listed below: 

| Escape Sequence | Description |
| --- | --- |
| \0 | Null character |
| \b | Backspace |
| \f | Form feed |
| \n | New line |
| \r | Carriage return |
| \t | Horizontal tab |
| \' | Single quote |
| \" | Double quote |
| \\ | Backslash |
| \a | Alert (bell) |
| \s | Space |

### What Each Escape Sequence Does

The following table shows the escape sequences and what they do:

* ***Null character***: The null escape sequence adds a null character to the string. This is a character with no value. It is used to terminate a string. It is not visible in the output.

* ***Backspace***: The backspace escape sequence moves the cursor back one space. It is used to overwrite the previous character.

* ***Form feed***: The form feed escape sequence moves the cursor to the beginning of the next page. It is used to start a new page.

* ***New line***: The new line escape sequence moves the cursor to the beginning of the next line. It is used to start a new line.

* ***Carriage return***: The carriage return escape sequence moves the cursor to the beginning of the current line.

* ***Horizontal tab***: The horizontal tab escape sequence moves the cursor a couple of spaces to the right in the same line.

* ***Single quote***: The single quote escape sequence adds a single quote to the string.

* ***Double quote***: The double quote escape sequence adds a double quote to the string.

* ***Backslash***: The backslash escape sequence adds a backslash to the string.

* ***Alert (bell)***: The alert escape sequence makes a sound. It is used to alert the user of something.

* ***Space***: The space escape sequence adds a space to the string.

