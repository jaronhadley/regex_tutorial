# Regex Walkthrough - Matching an Email

## Matching an Email

This regex string will match an email address.

        /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

At a high level the string is evaluating for acceptable string values between a `@` and a `.` (period). Acceptable values are defined as lower case letters, numbers, ( `_` )under score, hyphens and periods.

#### Note: A regex is considered a literal, so the pattern must be wrapped in slash characters (/)


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Bracket Expressions](#bracket-expressions)
- [Putting It All Together](#putting-it-all-together)


## Regex Components

### Anchors
`^` and `$` are both considered anchors. `^` Signfies that the start of the line will be immediately followed by the next values in the regex string while `$` indicates that the preceeding regex values will have immediately preceeded the end of the string

In this example we are stating that the email address must start with the `([a-z0-9_\.-]+)` query and end with the `([a-z\.]{2,6})` query
### Quantifiers
In this example there are 2 quantifiers used `+` and `{min,max}`

`+` means one or more of the preceeding query `[a-z0-9_\.-]` and  `{2,6}` means between 2 (min) and 6 (max) of the preceeding query `[a-z\.]`.

### Character Classes
Character classes allow for multiple values to be considered without including all values in bracket expression or a literal.

In this example the one character class that is used allows us to reference all digits by simply supplying `\d` instead of `[0-9]` or `[0123456789]`.

### Bracket Expressions
`[ ]` anything inside of a set of square brackets is a range of characters we want to match. In our example we are trying to match acceptable values for an email and we define acceptable values as:
- `a-z` lower case letters from a to z
- `0-9` any digit
- `_` underscores
- `\.` periods (because a period is a meta character we need the preceeding `\` to reference it as a literal period)
- `-` hyphens

Thus enclosing these values in `[ ]` we are stating that we will accept any of these values.

### Putting it all together

In Summary our regex is asking the following question:

Where can I find all of my accepted values (`[a-z0-9_\.-]`) at the beginning of a string (`^`) in one or more sequences (`+`) followed by an `@` which is followed by a string of digits, lower case letters, periods and hyphens (`[\da-z\.-]`) with a length of at least one charater (`+`) capped off by a period `\.` followed by a string of lower case letters or periods (`[a-z\.]`) somewhere between 2 and six characters long (`{2,6}`) at the end of the string (`$`).

## Author

Jaron Hadley is a developer in development. You can see his work on github. [Github](https://github.com/jaronhadley)
