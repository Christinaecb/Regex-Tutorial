# Regex Tutorial

Regex, short for regular expression, is a sequence of characters that defines a search pattern. It is commonly used in programming and text processing to match and manipulate text based on specific rules or patterns. These expressions are extremely useful for extracting data like phone numbers, emails, etc that follow a specific pattern from text, and they can be used in almost any programming language including JavaScript. Regex is a powerful tool for text parsing and searching, allowing users to perform complex operations on large amounts of data quickly and efficiently. It is supported in many programming languages and text editors, and has a wide range of applications in web development, data analysis, and system administration.

## Summary

In this tutorial I will break down the following regex for matching an email /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ into its basic components. This regex would be useful for validating email input in various applications.

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

### Anchors

This regex uses the anchors ^ which denotes the start of the string and $ which denotes the end of the string. Multiline is not enabled so the markers indicate start and end of a string as opposed to a line.

### Quantifiers

The quantifiers +, which means one or more, and {x, y} where x is the min and y is the max are used in this regex. For example, the first + means one or more characters that satisfy the requirements of [a-z0-9_\.-], the later + similarly denotes one or more characters in the group [\da-z\.-], and the {2, 6} indicates two to six characters in the group [a-z\.].

### OR Operator

The [] OR operator is used in this regex. For example, [a-z0-9_\.-] means any character a-z (case insensitive), any digit 0-9, _, ., or -. The \ is used to denote a literal . instead of the usual meaning of . which is "any character".

### Character Classes

This regex uses the character class \d which denotes any digit character 0-9. The \ indicates the character class which is distinct from a plain d meaning literally the letter d.

### Flags

The regex is enclosed by two / characters with no flags. Since multi-line is not enabled (by following the ending / with an m), the anchors match a string instead of the start and end of a line.

### Grouping and Capturing

Parenthases are used to group parts of the expression together. In /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ the username is grouped, then the provider name is grouped, but between them is an @ symbol so nothing affecting those groups affects the @ symbol and the regex will just look for a single @ symbol between those two groups.

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
