# Regex Tutorial

Regex, short for regular expression, is a sequence of characters that defines a search pattern. It is commonly used in programming and text processing to match and manipulate text based on specific rules or patterns. These expressions are extremely useful for extracting data like phone numbers, emails, etc that follow a specific pattern from text, and they can be used in almost any programming language including JavaScript. Regex is a powerful tool for text parsing and searching, allowing users to perform complex operations on large amounts of data quickly and efficiently. It is supported in many programming languages and text editors, and has a wide range of applications in web development, data analysis, and system administration.

## Summary

In this tutorial I will break down the following regex for matching an email `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` into its basic components. This regex would be useful for validating email input in various applications.

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

This regex uses the anchors ```^``` which denotes the start of the string and ```$``` which denotes the end of the string. Multiline is not enabled so the markers indicate start and end of a string as opposed to a line. 

### Quantifiers

The quantifiers ```+```, which means one or more, and ```{x, y}``` where ```x``` is the min and ```y``` is the max are used in this regex. For example, the first ```+``` means one or more characters that satisfy the requirements of ```[a-z0-9_\.-]```, the later ```+``` similarly denotes one or more characters in the group ```[\da-z\.-]```, and the ```{2, 6}``` indicates two to six characters in the group ```[a-z\.]```. 

### OR Operator

The ```[]``` OR operator is used in this regex. For example, ```[a-z0-9_\.-]``` means any character ```a-z``` (case insensitive), any digit ```0-9```, ```_```, ```.```, or ```-```. The ```\``` is used to denote a literal ```.``` instead of the usual meaning of ```.``` which is "any character". 

### Character Classes

This regex uses the character class ```\d``` which denotes any digit character 0-9. The ```\``` indicates the character class which is distinct from a plain ```d``` meaning literally the letter ```d```. 

### Flags

The regex is enclosed by two ```/``` characters with no flags. Since multi-line is not enabled (by following the ending ```/``` with an ```m```), the anchors match a string instead of the start and end of a line. 

### Grouping and Capturing

In this regex, ```()``` parentheses are used to capture a group. The first set of ```()``` captures the username of the email address, the second set captures the domain name, and the final set captures the domain. Broken down, ```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/``` means one or more characters ```a-z``` (case insensitive), ```0-9```, ```_```, ```.```, or ```-```, followed by a literal ```@```, followed by one or more characters of any digit ```0-9```, ```a-z``` (case insensitive), ```.```, or ```-```, followed by a literal ```.```, followed by 2-6 characters ```a-z``` (case insensivite) or ```.```. 

### Bracket Expressions

Using brackets allows a regex to match specific characters in a range. So, `[a-z]` is not looking for a or - or z, but actually looking for any letters a through z. And in the brackets the "-" is not taken literally in the cases of a-z or 0-9. But after the \ to escape the period it is recognized as a literal "-".

### Greedy and Lazy Match

In regular expressions (regex), "greedy" and "lazy" matching are two different ways of specifying how a pattern should match text.

A "greedy" match means that the pattern should try to match as much text as possible while still satisfying the overall pattern. This means that the regex engine will match as many characters as it can, even if it could have matched the pattern with fewer characters. In other words, greedy matching matches as much text as possible while still allowing the pattern to be matched.

For example, if you have the string `"abc123def"` and the pattern `/a.d/`, a greedy match will match the entire string `"abc123def"`, because the . will match `"bc123"`.

A "lazy" match, on the other hand, means that the pattern should match as little text as possible while still satisfying the overall pattern. This means that the regex engine will match as few characters as it can, even if it could have matched the pattern with more characters. In other words, lazy matching matches as little text as possible while still allowing the pattern to be matched.

For example, if you have the string `"abc123def"` and the pattern `/a.?d/`, a lazy match will only match the characters `"abc1d"`, because the .? will match "nothing or the minimum of any character" and satisfy the pattern as soon as it sees the `"d"`.

In summary, the difference between greedy and lazy matching is in how the regex engine tries to match text. Greedy matching matches as much text as possible, while lazy matching matches as little text as possible.

### Boundaries

In regular expressions (regex), a boundary is a character or a sequence of characters that define the start or end of a word, line, or string. A regex boundary is a way to specify a position between two characters or sets of characters that can be matched by a pattern.

There are several types of regex boundaries that can be used depending on the context and the type of match required:

Word boundary `(\b)`: A word boundary is a zero-width assertion that matches the position between a word character (as defined by the Unicode standard) and a non-word character, or vice versa. It is often used to match whole words within a string.

Line boundary `(^ and $)`: The caret `(^)` matches the start of a line, while the dollar sign `($)` matches the end of a line. These boundaries are often used to match a pattern at the beginning or end of a line.

Lookahead and lookbehind assertions: Lookahead assertions allow you to match a pattern only if it is followed by another pattern, without including the second pattern in the match. Lookbehind assertions allow you to match a pattern only if it is preceded by another pattern, without including the first pattern in the match.

Using regex boundaries in your regular expressions can help you create more specific and accurate patterns that match the exact parts of a string that you need.

### Back-references

In regular expressions, a back-reference is a way to reference a previously captured group in the same regex. It is created by capturing a group of characters using parentheses, and then referencing that group later in the regex using a special syntax. Back-references are useful for matching repeating patterns or patterns with symmetry.

For example, consider the following regex pattern: `/(ab)+\1/`. This pattern matches a string that contains one or more occurrences of the characters "ab", followed by the exact same sequence of characters that was matched by the first group (i.e., the "\1" back-reference).

Here's how it works:

The pattern `/(ab)+/` matches one or more occurrences of the characters "ab" and captures them in group 1.
The "\1" back-reference then references group 1 and matches the exact same sequence of characters that was captured by the first group.
So, this pattern would match strings like `"abab"`, `"ababab"`, `"abababab"`, and so on, but it would not match strings like `"aba"` or `"abba"`.

Back-references can be very useful in situations where you need to match patterns that repeat or that have some sort of symmetry. They allow you to create more complex patterns that can match a wider range of strings.

### Look-ahead and Look-behind

In regular expressions, look-ahead and look-behind assertions are non-capturing zero-width patterns that match text based on what comes before or after a particular pattern, without including those characters in the match. Look-ahead checks what follows the pattern, while look-behind checks what precedes it. They are useful for creating more complex patterns that match specific text only when it is preceded or followed by certain other text.

There are two types of look-arounds:

Positive Look-ahead: (?=...): Checks if a pattern exists ahead of the current position, without including it in the match result. If the pattern exists, the match continues from the current position. For example, the pattern /\d(?=\w)/ would match any digit that is immediately followed by a word character.

Negative Look-ahead: (?!...): Checks if a pattern does NOT exist ahead of the current position, without including it in the match result. If the pattern does not exist, the match continues from the current position. For example, the pattern /hello (?!world)/ would match "hello there" but not "hello world".

There are also two types of look-behinds, which work in a similar way to look-aheads:

A negative look-behind assertion is specified using the syntax "(?<!pattern)", which matches only if "pattern" does not match the text immediately preceding the current position.

Positive Look-behind Checks if a pattern exists behind the current position, without including it in the match result. If the pattern exists, the match continues from the current position. For example, the pattern /(?<=\w)\d/ would match any digit that is immediately preceded by a word character.

For the example I'm researching, `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, the look-ahead in this expression is the `(?=\.([a-z.]{2,6})$)` part, which is used to ensure that the email address ends with a valid top-level domain. It looks ahead of the current position to check if the next characters match the specified pattern. In this case, it matches a dot followed by 2 to 6 lowercase alphabets or dots until the end of the string. If the look-ahead fails, the entire match fails.

## Author

[GitHub Profile](https://github.com/Christinaecb)

Email -- christina.e.c.barberi@gmail.com

I welcome feedback and suggestions for this project. If you have ideas for how to improve the project, please feel free to contact me directly. Your input is greatly appreciated!
