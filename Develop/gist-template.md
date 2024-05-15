Regex Tutorial: Understanding the URL Validation Pattern

Introduction
Welcome to this tutorial on regex (regular expressions). In this guide, we'll break down a specific regex pattern used to validate URLs. By the end of this tutorial, you will understand how this pattern works and how to apply it in your web development projects.

Summary
The regex pattern we'll be discussing is commonly used to validate URLs. Here's the pattern:
^(https?|ftp):\/\/[^\s/$.?#].[^\s]*$
This pattern ensures that the input follows the standard URL format, including the protocol, domain, and optional path.

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
Anchors are used to assert the position of the match within the input string. In our regex, we use the caret ^ to indicate the start of the string and the dollar sign $ to indicate the end of the string.

^ ... $

Example:

Valid: https://example.com
Invalid: example.com https://

### Quantifiers
Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. In our regex, the ? quantifier indicates that the preceding element (in this case, s) is optional, appearing 0 or 1 time.

https?

Example:

Valid: http
Valid: https

### OR Operator
The OR operator | is used to match either of the patterns separated by it. In our regex, it matches either http or https.

https?|ftp

Example:

Valid: http
Valid: https
Valid: ftp

### Character Classes
Character Classes
Character classes match any one of a set of characters. The character class [^\s/$.?#] matches any character except whitespace characters, /, ., $, ?, and #.

Code Snippet:

ruby
Copy code
[^\s/$.?#]
Example:

Valid: a
Valid: 1
Invalid: (space)

### Flags
Flags are optional parameters that modify the behavior of the regex. Common flags include i for case-insensitive matching and g for global matching. Our regex does not use any flags.

Code Snippet:

bash
Copy code
/pattern/flags
Example:

/pattern/i matches Pattern, pattern, PaTtErN
### Grouping and Capturing
Grouping allows us to treat part of a regex as a single unit. In our regex, (https?|ftp) groups the protocols so that the | operator can apply to all of them.

Code Snippet:

scss
Copy code
(https?|ftp)
Example:

Valid: http
Valid: https
Valid: ftp

### Bracket Expressions
Bracket expressions (character classes) match any one of the characters inside the brackets. In our regex, [^\s/$.?#] is a negated character class that matches any character except those listed.

Code Snippet:

ruby
Copy code
[^\s/$.?#]
Example:

Valid: a
Invalid: /

### Greedy and Lazy Match
Greedy quantifiers match as much of the input as possible, while lazy quantifiers match as little as possible. Our regex uses a greedy match by default.

Code Snippet:

css
Copy code
[^\s]*$
Example:

Valid: example
Valid: example/path

### Boundaries
Boundaries match a position, not a character. The \b boundary matches a word boundary. Our regex does not explicitly use word boundaries.

Code Snippet:

css
Copy code
\bword\b
Example:

Valid: word (spaces on both sides)
Invalid: word! (no space on right side)

### Back-references
Back-references match the same text as previously matched by a capturing group. Our regex does not use back-references.

Code Snippet:

scss
Copy code
(\w)\1
Example:

Valid: aa
Invalid: ab
### Look-ahead and Look-behind
Look-ahead and look-behind assertions check for a match without including it in the result. Our regex does not use these assertions.

Code Snippet:

css
Copy code
(?=.*[0-9])
Example:

Valid: abc123
Invalid: abcdef
## Author

This tutorial was created by Tabitha Ledford, a student at the Coding BootCamp hosted by the University of Minnesota. 

https://github.com/Tabi-Led
