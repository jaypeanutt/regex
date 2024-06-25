# Reggex Tutorial
As a web development student, I have developed a tutorial explaining the breakdown of a specific regex and how it works.

## Summary

A Regex or regular expression is a sequence of characters that define a search pattern. Usually the patterns are used by string-searching algorithms for "find" or "find and replace" operations on strings. It also searches for input validations. It is a technique commonly developed in theoretical computer science.

We will look ar a string of code using regex, this code is used to validate a password's strength..

Example:'^(?=.*[A-Z])(?=.*[a-z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$'

The below content will explain what each section of this code does/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components
1. '^': Asserts the start of the line.
2. '(?=.*[A-Z])': Positive lookahead assertion ensuring that the string contains at least one uppercase letter. This part ensures that there is at least one uppercase letter somewhere in the string.
3. '(?=.*[a-z])': Positive lookahead assertion ensuring that the string contains at least one lowercase letter. This part ensures that there is at least one lowercase letter somewhere in the string.
4. '(?=.*\d)': Positive lookahead assertion ensuring that the string contains at least one digit. This part ensures that there is at least one digit somewhere in the string.
5. '(?=.*[@$!%*?&])': Positive lookahead assertion ensuring that the string contains at least one special character from the set [@$!%*?&]. This part ensures that there is at least one special character from the specified set somewhere in the string.
6. '[A-Za-z\d@$!%*?&]{8,}': Matches any combination of letters (upper or lowercase), digits, or special characters [@$!%*?&], with a minimum length of 8 characters. This part ensures that the string contains at least 8 characters, including any combination of letters (upper or lowercase), digits, or special characters from the specified set.
7. '$': Asserts the end of the line.
So, altogether, this regex ensures that the input string meets specific password complexity requirements, including having at least one uppercase letter, one lowercase letter, one digit, one special character from the specified set, and a minimum length of 8 characters.

### Anchors
The '^' and '$' symbols are used as anchors:

'^': Asserts the start of the line. It ensures that the pattern starts matching from the beginning of the input string.
'$': Asserts the end of the line. It ensures that the pattern matches until the end of the input string.

### Quantifiers
The quantifiers '*' and '{8,}' are used:
1. .*: This quantifier matches zero or more occurrences of any character (.), including none (*). In this pattern, it's used within positive lookahead assertions '(?=.*[A-Z])', '(?=.*[a-z])', '(?=.*\d)', and '(?=.*[@$!%*?&])'. These assertions are ensuring that the characters they're looking for (uppercase letters, lowercase letters, digits, and special characters) can occur anywhere in the string, including multiple times or not at all.
2. '{8,}': This quantifier matches 8 or more occurrences of the preceding element. In this pattern, it's used at the end [A-Za-z\d@$!%*?&]{8,}, ensuring that the string contains at least 8 characters from the specified character set (letters, digits, and special characters).
### OR Operator
There isn't an explicit OR operator (|) used. However, the pattern is employing multiple positive lookahead assertions, each ensuring the presence of different character types '([A-Z]', '[a-z]', '\d', and '[@$!%*?&])'. These assertions together function similarly to an OR operator, ensuring that at least one character from each character class is present in the string.

So, while the pattern doesn't use the | OR operator explicitly, it effectively enforces the requirement that the string must contain characters from each of the specified classes (uppercase letter, lowercase letter, digit, and special character) using positive lookahead assertions.

### Character Classes
1. '[A-Z]': Matches any uppercase letter from A to Z.
2. '[a-z]': Matches any lowercase letter from a to z.
3. '\d': Matches any digit (equivalent to '[0-9])'.
 Character classes, denoted by square brackets '[ ]', define a set of characters from which the regex engine will match a single character in the input string.

### Flags
There are no flags included. This pattern is a simple string pattern without any flags specified. The pattern itself consists of positive lookahead assertions and character classes to enforce specific requirements for validating passwords.

Common flags include:

'g': Global matching, which finds all matches in the input string rather than stopping after the first match.
'i': Case-insensitive matching, which ignores the case of letters when matching.
'm': Multiline mode, which treats the beginning '(^)' and end '($)' anchors as matching the start and end of lines within the input string rather than the entire string.
### Grouping and Capturing
There are no explicit groups or capturing groups defined in the tutorial reggex.

Grouping and capturing ex:
1. '(\d{4})': Capturing group for the year, which consists of four digits \d{4}.
2. '-': Matches the hyphen separator between year and month.
3. '(\d{2})': Capturing group for the month, which consists of two digits \d{2}.
4. '-': Matches the hyphen separator between month and day.
'(\d{2})': Capturing group for the day, which consists of two digits \d{2}.
### Bracket Expressions
1. '[A-Z]': Matches any uppercase letter from A to Z.
2. '[a-z]: Matches any lowercase letter from a to z.
3. '\d': Matches any digit (equivalent to [0-9]).
4. '[A-Za-z\d@$!%*?&]': Matches any character that is either a letter (upper or lowercase), a digit, or one of the specified special characters '@$!%*?&'.
The term "Bracket Expressions" usually refers to character classes, which are enclosed within square brackets '[ ]' in regex.
### Greedy and Lazy Match
.'*': This is a greedy match, meaning it matches as many characters as possible (including none) while still allowing the rest of the pattern to match.
1. Greedy quantifiers '(*, +, ?, {})' match as much of the string as possible, while still allowing the overall pattern to match. They match as many characters as they can initially and then backtrack if needed to make the overall pattern match.
2. Lazy quantifiers '(*?, +?, ??, {}); match as little as possible, matching as few characters as needed to satisfy the pattern.
### Boundaries
The '^'and '$' symbols are used to denote boundaries:

'^': Asserts the start of the line. It ensures that the pattern starts matching from the beginning of the input string.
'$': Asserts the end of the line. It ensures that the pattern matches until the end of the input string.

### Back-references
There are no explicit back-references used. 
Back-references are used to refer back to captured groups within the regex pattern itself. They are denoted by '\1', '\2', etc., and reference the content of captured groups based on their order of appearance.

### Look-ahead and Look-behind
1. '(?=.*[A-Z])': Positive lookahead assertion ensuring that the string contains at least one uppercase letter '([A-Z])'.
2. '(?=.*[a-z])': Positive lookahead assertion ensuring that the string contains at least one lowercase letter '([a-z])'.
3. '(?=.*\d)': Positive lookahead assertion ensuring that the string contains at least one digit (\d).
4. '(?=.*[@$!%*?&])': Positive lookahead assertion ensuring that the string contains at least one special character from the specified set '([@$!%*?&])'.

There are no look-behind assertions in this pattern. Look-behind assertions '(?<=...)' work the same as lookaheads but check the characters behind the current position in the string. However, this pattern focuses on lookahead assertions to enforce the specified conditions.


## Author
I am Angel Escobedo.
Here's a link to my [github profile](https://github.com/jaypeanutt)