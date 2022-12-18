# Regex Tutorial



## Summary

A tutorial that explains how a specific regular expression, or regex, functions by breaking down each part of the expression and describing what it does. 

For example ``` ([A-Za-z0-9-]+) ```

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

In regular expressions, an anchor is a symbol that matches a position in the input string rather than a specific character. There are two types of anchors:

* **Start-of-line (SOL) anchor**: The SOL anchor ```(^)``` matches the position at the beginning of a line. For example, the regular expression ```^The``` will match "The" at the start of a line, but it will not match "The" if it appears later in a line.

* **End-of-line (EOL) anchor**: The EOL anchor ```($)``` matches the position at the end of a line. For example, the regular expression ```end$``` will match "end" at the end of a line, but it will not match "end" if it appears earlier in a line.

#### Example

Here are some examples of how anchors can be used in regular expressions:

To match a string that starts with "The" and ends with "end", you can use the regular expression ```^The.*end$```. The ```^``` anchor will match the start of the line, and the ```$``` anchor will match the end of the line.

To match a string that starts with a digit, you can use the regular expression ```^[0-9]```. The ```^``` anchor will match the start of the line, and the character class ```[0-9]``` will match any digit.

To match a string that ends with a whitespace character, you can use the regular expression ```.[ \t\r\n]$```. The ```.``` pattern will match any number of characters, and the character class ```[ \t\r\n]``` will match a whitespace character. The ```$``` anchor will match the end of the line.

### Quantifiers

In regular expressions, a quantifier is a symbol that specifies the number of times a character, group, or character class should be repeated in the input string. There are several types of quantifiers:

* **The greedy quantifier**: The greedy quantifier (e.g.,``` ```, ```+```, ```?```) matches as many characters as possible, while still allowing the overall regular expression to match. For example, the regular expression ```.``` will match any number of characters, including zero characters.

* **The lazy quantifier**: The lazy quantifier (e.g.,``` ?```, ```+?```, ```??```) is similar to the greedy quantifier, but it matches as few characters as possible, while still allowing the overall regular expression to match. For example, the regular expression ```.?``` will match zero or more characters, but it will try to match as few characters as possible.

* **The exact quantifier**: The exact quantifier (e.g., ```{n}```, ```{n,}```, ```{n,m}```) allows you to specify the exact number of times a character, group, or character class should be repeated. For example, the regular expression ```a{3}``` will match "aaa" but not "aa" or "aaaa".

* **The possessive quantifier**: The possessive quantifier (e.g., ```*+```, ```++```,```?+```) is similar to the greedy quantifier, but it does not backtrack. This means that once the quantifier has matched as many characters as it can, it will not give them up, even if doing so would allow the overall regular expression to match.

#### Examples

Here are some examples of how quantifiers can be used in regular expressions:

* To match any number of digits, you can use the regular expression ```\d*```. The ```\d``` character class will match any digit, and the ```*``` quantifier will match zero or more digits.

* To match a string that contains at least one digit, you can use the regular expression ```\d+```. The ```\d``` character class will match any digit, and the ```+``` quantifier will match one or more digits.

* To match a string that contains three letters, you can use the regular expression ```[a-zA-Z]{3}```. The character class ```[a-zA-Z]``` will match any letter, and the ```{3}``` quantifier will match exactly three letters.

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
