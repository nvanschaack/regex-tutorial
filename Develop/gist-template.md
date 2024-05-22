# Email Regex Tutorial

In this tutorial, I will be explaining and deconstructing a regex for an email search pattern. The regex I have selected, /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ , is used specifically to verify user input to validate the input is a valid email address. 

## Summary

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

This regex pattern is commonly used to validate email addresses. It checks for a pattern where there are characters before the '@' symbol, followed by characters after the '@' symbol, a dot, and then 2 to 6 characters for the top-level domain.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Escapes](#character-escapes)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions/ Positive Character Group](#bracket-expressions-positive-character-group)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

**/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/**

When using literal notation, you define a regex similar to a string or number and it is considered a literal. We use "/" to indicate the beginning and end of the entire (literal) regex. Another notation would be RegExp, which uses quotes instead of slashes and is not used in this example.

### Anchors

An anchor can be either ^ or $.
^ : Asserts the start of a string. Whatever comes after the "^" anchor are the characters or range of possible matches that will begin the regex.
$ : Asserts the end of a string. Whatever precedes the "$" anchor are the characters or range of possible matches that are at the end of the regex.

### Quantifiers/ Greedy Match

+ : Indicates that the preceding characters or range of characters can appear **one or more** times.
So, ([a-z0-9_\.-]+) means the regex matches **one or more** occurrences of lowercase letters, digits, underscore, dot, or hyphen before the '@' symbol. The ([\da-z\.-]+) group means the match needs **one or more** occurrences of digits, lowercase letters, dot, or hyphen after the '@' symbol in the domain name. Having the "+" makes certain that there is **at least one** valid character before the "@". This is why quantifiers are "greedy"; they want to match as many number of characters possible.

{2,6} : This is a way to set limits to whatever follows the "." in an email address (e.g., .com, .org). The sequence preceding the "{2,6}" which is [a-z\.] should have a **minimum of 2** characters and a **maximum of 6** characters.

### OR Operator
n/a

### Character Escapes

\ : This is used to escape the character preceding the back slash being used literally. In the email regex, "\." matches a literal dot '.'.

### Character Classes

\d : This is shorthand for [0-9]. This means that any single digit (0-9) character can be used in the domain name of an email. 

### Flags
n/a 

### Grouping and Capturing

() : A way to group sections of the regex. Each section is called a subexpression. In the email regex, there are 3 subexpressions: ([a-z0-9_\.-]+), ([\da-z\.-]+), and ([a-z\.]{2,6}). 

### Bracket Expressions/ Positive Character Group

[] : Any characters inside of brackets represent a combination of characters that you want to match. In other words, anything inside of the brackets are some characters you want to include in your match- it can be **any OR all** of them.

### Boundaries
n/a

### Back-references
n/a

### Look-ahead and Look-behind
n/a 

## Author

This tutorial was created by Nell Van Schaack.
-[My GitHub](https://github.com/nvanschaack)