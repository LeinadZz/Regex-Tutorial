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

#### Examples

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

In regular expressions, grouping constructs are used to group characters, character classes, or other regular expressions together and to apply quantifiers to the entire group. There are several types of grouping constructs:

* **Capturing group**: A capturing group (e.g., (pattern)) captures the text matched by the group and stores it in a numbered group. You can then use backreferences to refer to the captured text later in the regular expression or in the replacement string of a search-and-replace operation.

* **Non-capturing group**: A non-capturing group (e.g., (?:pattern)) groups characters, character classes, or other regular expressions together, but it does not capture the text matched by the group. Non-capturing groups are useful when you want to apply a quantifier to a group of characters, but you don't need to capture the group's match.

* **Positive lookahead**: A positive lookahead (e.g., (?=pattern)) is a zero-width assertion that asserts that the characters following the current position in the input string match the pattern inside the lookahead. The lookahead does not consume any characters, so it does not contribute to the overall match.

* **Negative lookahead**: A negative lookahead (e.g., (?!pattern)) is similar to a positive lookahead, but it asserts that the characters following the current position in the input string do not match the pattern inside the lookahead.

Here are some examples of how grouping constructs can be used in regular expressions:

To match a string that contains a word surrounded by parentheses, you can use the regular expression "( ( \w+ ) )". The capturing group (\w+) will capture the word inside the parentheses, and the backreference \1 can be used to refer to the captured text later in the regular expression or in the replacement string of a search-and-replace operation.

To match a string that contains a word followed by a space and a digit, you can use the non-capturing group "(?:\w+ )\d". The non-capturing group (\w+ ) will group the word and the space together, and the \d character class will match the digit.

To match a string that contains a word followed by a space and the word "cat", you can use the positive lookahead "(\w+ )(?=cat)". The capturing group (\w+ ) will capture the word, and the positive lookahead (?=cat) will assert that the characters following the word are "cat".

### Character Classes

In regular expressions, a character class is a set of characters enclosed in square brackets ```([ and ])```. A character class matches any single character that is a member of the class. There are several types of character classes:

* **Predefined character classes**: There are several predefined character classes that you can use to match common types of characters. These include ```\d (any digit)```, ```\w (any word character)```, ```\s (any whitespace character)```, and ```\b (a word boundary)```.

* **Negated character classes**: You can negate a character class by placing a caret ```(^)``` at the beginning of the class. A negated character class matches any single character that is not a member of the class. For example, ```[^\d]``` will match any character that is not a digit.

* **Range of characters**: You can specify a range of characters by separating the start and end characters with a hyphen ```(-)```. For example, ```[a-z]``` will match any lowercase letter, and ```[A-Z0-9]``` will match any uppercase letter or digit.

* **Union of character classes**: You can use the pipe symbol ```(|)``` to specify a union of character classes. For example, ```[a-z|A-Z]``` will match any letter, and ```[\d|\w]``` will match any digit or word character.

#### Examples

Here are some examples of how character classes can be used in regular expressions:

To match a string that contains only digits, you can use the regular expression ```^\d+$```. The ```^``` anchor will match the start of the line, the ```\d``` character class will match any digit, and the ```+``` quantifier will match one or more digits. The ```$``` anchor will match the end of the line.

To match a string that contains a single uppercase letter or digit, you can use the regular expression ```[A-Z0-9]```. The character class ```[A-Z0-9]``` will match any uppercase letter or digit.

To match a string that contains a word followed by a punctuation mark, you can use the regular expression ```\w+[.,;:!?]```. The ```\w``` character class will match any word character, and the ```+``` quantifier will match one or more word characters. The character class ```[.,;:!?]``` will match any punctuation mark.

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
