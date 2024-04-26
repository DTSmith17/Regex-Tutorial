# Regex Tutorial

## Overview
This tutorial is an introduction to the key concepts and practical use of regular expressions (Regex). Using an email matching pattern `(/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/)` , it explores various components that make up Regex and how they work together to identify patterns in strings.

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
Anchors in regular expressions are special characters that define the start and end points of a string. In the Regex pattern `/^([a-z0-9_.-]+)@([\da-z.-]+)\.([a-z.]{2,6})$/`, the caret `^` and dollar sign `$` serve as anchors to indicate where the pattern should start and where it should end.

- The caret `^` is the start anchor, indicating that the pattern must begin at the beginning of the string. It acts as a boundary, ensuring that the pattern does not match partial segments from the middle or end of a string.

- The dollar sign `$` is the end anchor, marking the point where the pattern must conclude. It ensures that the pattern does not continue beyond this point or include additional trailing characters.

It's important to note that these anchors do not represent specific characters that are matched. Instead, they function as guideposts, indicating the boundaries of the pattern. By using these anchors, the Regex pattern is designed to precisely match the entire string from start to finish, preventing unintended matches that may occur if only a part of the string met the criteria.

### Quantifiers

In the regular expression `/^([a-z0-9_.-]+)@([\da-z.-]+)\.([a-z.]{2,6})$/`, quantifiers are used to define the rules and constraints for what a string can contain. They create boundaries within which the input must fit, enforcing specific guidelines that the Regex pattern follows.

- The `+` quantifier indicates that the specified set of characters must appear at least once. In this pattern, there are two `+` quantifiers. The first one requires at least one character from the set `[a-z0-9_.-]`, while the second one requires at least one character from the set `[\da-z.-]`. This ensures that the local part and the domain of the email address contain at least one character each.

- The `{2,6}` quantifier is a bracket quantifier, setting a range for the number of times a character can occur. In this pattern, it applies to the last part, specifying that the top-level domain must contain at least two characters but no more than six. This flexibility allows for variations in domain extensions while ensuring they are within the acceptable range.

Quantifiers in Regex play a crucial role in establishing the expected behavior of the pattern, ensuring that it matches the right structure and follows the given constraints.


### OR Operator
The OR operator (`|`) allows for alternate matching patterns. For instance, the following Regex pattern for dates allows different formats: `^(0[1-9]|1[012])[-/.](0[1-9]|[12][0-9]|3[01])[-/.][0-9]{4}$`.

The initial group `^(0[1-9]|1[012])` allows users to choose a month beginning with either a '0' or a '1', followed by the appropriate set of numbers. This OR operator (`|`) facilitates selecting between different possible patterns, providing flexibility within defined boundaries.