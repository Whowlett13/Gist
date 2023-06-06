# Title Password Validator

Brief Regex description and is basic components of what a Regex (regular expression) consists of and an example use case for when manipulating a text search for a password validation.

## Summary

A regular expression for a Password that will contain at least one uppercase letter, lowercase letter, digit and special symbol.

- Matching a password validation: `/(?=._\d)(?=._[a-z])(?=._[A-Z])(?!._\s)(?=._[!@#$_])/g`

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components Breakdown

let passwordValidator = `/^(?=._\d)(?=._[a-z])(?=._[A-Z])(?!._\s)(?=._[!@#$_])/g`;

- `()` => will create a group for the search defined inside the ().

- `(?=..)` => Is a syntax for a positive look ahead in regex. It asserts that the following pattern should match but does not consume any characters or include them in the final match.

- `.*` => Will match any characters (except new lines) zero or more times.

- `\d` => Will match a single digit character (0-9).

- `._[a-z]` => Checks if the input string contains a character followed by an underscore, followed by a lowercase letter.

-`._[A-Z]` => Checks if the input string contains a character followed by an underscore, followed by a uppercase letter.

- `(?!..)` => This is the syntax for a negative look ahead It asserts that the following pattern should not match. If the pattern is matched, the entire match fails.

- `\s` => This matches any whitespace character, such as a space or tab.

- `[!@#$_]` => This character class matches a single character that is either a `!`, `@`, `#`, `$`, or `_`.

### Anchors

- Caret `^` => Beginning or a string or line.

- -`\d` => Will match a single digit character (0-9).

Example in code:

- `^(?=._\d)` Will check for the password starting on a new line and \d will match a single digit character (0-9).

### Quantifiers

- `(?=)`=> checks patterns as a positive lookahead. Will check for anything before and not include the search it self.

- `(?!..)` => This is the syntax for a negative look ahead.

Example in code:

- `(?=..)` => Is a syntax for a positive look ahead in regex. Will check for anything after and not include the search it self.
- `(?!..)` => This is the syntax for a negative look ahead. Will check for anything before and not include the search it self.

### Grouping Constructs

- `(..)` => Is the grouping constructor that will separate each search value in its own group.

Example in code:

- `(?=._\d)` => Is a group for checking if the current position in the string is followed by a character, an underscore, and a digit.

- `(?=._[a-z])` => Is a group for checking if the current position in the string is followed by a character, an underscore, and a lowercase letter from a-z.

- `(?=._[A-Z])` => Is a group for checking if the current position in the string is followed by a character, an underscore, and a Uppercase letter from A-Z.

- `(?!._\s)` => is a Group for checking if the current position in the string is not followed by a character, any character, and a whitespace character.

- `(?=._[!@#$_])` => is a group for checking if the current position in the string is followed by a character, an underscore, and one of the specific characters mentioned.

### Bracket Expressions

- `[..]` => Used to define a character class or a bracket expression. They allow you to specify a set of characters from which a single character is expected to match.

Example in code:

- `[a-z]` => Will check for a Uppercase letter from A-Z.

- `[A-Z]`=> Will check for a lowercase letter from a-z.

### Character Classes

- `[]` => Is a character class is a set of characters enclosed within square brackets. It specifies the characters that will successfully match a single character from a given input string.

Example in code:

- `[a-z]` => Will check for a Uppercase letter from A-Z since its enclosed in `[]`.

- `[A-Z]`=> Will check for a lowercase letter from a-z since its enclosed in `[]`.

### The OR Operator

- `( || )` => returns the boolean value true if either or both operands is true and returns false otherwise.

### Flags

- `/..../g` => With this flag the search is case-insensitive: no difference between A and a.

  Example in code:
  `/..../g` => Creates a global flag

### Character Escapes

- `\` => Is used to escape a special character.

  Example in code:

  - `(?!._\s)(?=._[!@#$_])` => Will check the current position in the string is followed by a character, an underscore, and one of the specific characters mentioned.

## Author

- Wyatt Howlett
  Link to Github Gist: https://gist.github.com/Whowlett13/7459ff36c423d8e5afb94634f8f048ab

---

© 2023 edX Boot Camps LLC. Confidential and Proprietary. All Rights Reserved.
