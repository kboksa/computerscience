# Computer Science

Regular expressions are patterns used to match character combinations in strings. In a regular expression the metacharacter ^ means "not". So, while "a" means "match lowercase a", "^a" means "do not match lowercase a".

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
Anchors are a different breed. They do not match any character at all. Instead, they match a position before, after, or between characters. They can be used to “anchor” the regex match at a certain position. The caret ^ matches the position before the first character in the string. Applying ^a to abc matches a. ^b does not match abc at all, because the b cannot be matched right after the start of the string, matched by ^. See below for the inside view of the regex engine. Similarly, $ matches right after the last character in the string. c$ matches c in abc, while a$ does not match at all.

### Quantifiers

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
Quantifiers are used to communicate how many characters are expected. Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. By default, quantifiers are greedy, and will match as many characters as possible. If the ",+,?,{}" characters are found within regular expressions, they are considered quantifiers. The ? indicates the expression to match 0 or 1time. As mentioned in the summary above because there are 2 types of formats we'll use the or operator to distinguish which format we are using. In our Hex Value regular expression we have {6} (Hex Triplet Format) and {3} (Shorthand Hex Format), this indicates that the length of the component preceding these quantifiers should be 6 for {6} and 3 for {3}.

### Grouping Constructs

This expression looks for three (3) capturing groups.
([a-z0-9_\.-]+) : This is matching the user's email name. It is looking for a string containing lowercase a-z, digits 0-9, an underscore, a period, or a hyphen. If the string contains anything else, this verification will fail.
([\da-z\.-]+) : This group is looking for a string containing the email domain or service. It is expecting to receive only digits 0-9, lowercase letters a-z, a period, or a hypen. Again, if the regex receives anything other than these characters, the verification will fail.
([a-z\.]{2,6}) : The third group is looking for the final portion of the email address after the period. This is typically com, net, org etc. The regex is expecting to receive only lowercase letters or a period, and the string should be between 2 and 6 characters long.

### Bracket Expressions

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
Matches any character in the square brackets. For example [nN] [oO] matches no, nO, No, and NO. gr[ae]y matches both spellings of the word 'grey'; that is, gray and grey.

### Character Classes

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
Character classes are components within our regular expression that tells us what type of characters to expect. In our example our character classes are confined within brackets []. For our example we have 2 character classes: [a-f0-9] and [a-f0-9] which searches for the same values. We will be breaking down what the characters are searching within these character classes. a-f searches for letters a-f and 0-9 searches for digits 0-9.

### The OR Operator

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
The "or" operator within a regular expression is defined using the | element. The or operator indicates that it could either of the components that we are separating with the |. For our hex value regular expression we have ([a-f0-9]{6}`|`[a-f0-9]{3}). Note the or operator separating these 2 components. This means that our hex value could either be 6 characters [a-f0-9]{6} or 3 characters [a-f0-9]{3}.

### Flags

This regex currently uses no flags. With regular expressions, there are a total of six (6) optional flags. The g flag is one that is often used with an email regex, and it requires that the regular expression is tested against all possible matches in the string. Without the g flag, like in our example, it will test it only for the first class that the string matches.

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
