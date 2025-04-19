# Regular Expressions (Regex) Guide

## Overview
This guide provides a comprehensive introduction to Regular Expressions (regex), a powerful tool for searching, matching, and manipulating text patterns. Whether you're validating emails, parsing logs, or performing search-and-replace operations, this guide will help you master regex.

## Table of Contents
- [Introduction to Regular Expressions](#introduction-to-regular-expressions)
- [Basic Syntax](#basic-syntax)
- [Meta-characters](#meta-characters)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Anchors](#anchors)
- [Groups and Capturing](#groups-and-capturing)
- [Escape Characters](#escape-characters)
- [Examples](#examples)
- [Regex Flags](#regex-flags)
- [Practical Use Cases](#practical-use-cases)
- [Resources](#resources)

## Introduction to Regular Expressions
Regular Expressions (regex) are sequences of characters that define search patterns. They are widely used in text processing, validation, search engines, and databases to match and manipulate text efficiently.

## Basic Syntax
- **Literals**: Match exact strings (e.g., `abc` matches "abc").

## Meta-characters
Special characters with unique meanings:
- `^`: Start of string
- `$`: End of string
- `.`: Any character (except newline)
- `[]`: Character class
- `|`: OR operator
- `()`: Grouping

## Quantifiers
Specify how many times an element should appear:
- `*`: Zero or more
- `+`: One or more
- `?`: Zero or one
- `{n}`: Exactly n times
- `{n,}`: At least n times
- `{n,m}`: Between n and m times

## Character Classes
Define sets of characters to match:
- `\d`: Any digit (`[0-9]`)
- `\D`: Any non-digit
- `\w`: Any word character (`[a-zA-Z0-9_]`)
- `\W`: Any non-word character
- `\s`: Any whitespace
- `\S`: Any non-whitespace

## Anchors
Position patterns within a string:
- `^`: Start of string
- `$`: End of string
- `\b`: Word boundary
- `\B`: Non-word boundary

## Groups and Capturing
- `()`: Group patterns and capture matches
- `(?:...)`: Non-capturing group
- `\n`: Reference to the n-th captured group

## Escape Characters
Use `\` to match special characters literally (e.g., `\.` matches a period).

## Examples
1. **Email Validation**: `^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$`
   - Matches valid email addresses (e.g., `user@example.com`).
2. **US Phone Number**: `^\(\d{3}\) \d{3}-\d{4}$`
   - Matches phone numbers like `(123) 456-7890`.

## Regex Flags
Modify regex behavior:
- `i`: Case-insensitive
- `g`: Global search
- `m`: Multiline mode

## Practical Use Cases
- Validate email addresses
- Search and replace text in editors or scripts
- Extract data from logs or datasets

## Resources
- [Regular Expressions 101](https://regex101.com/) - Online regex tester and debugger
- [MDN Regular Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) - Comprehensive guide

## Getting Started
1. Learn the syntax and meta-characters.
2. Test patterns using tools like [Regex101](https://regex101.com/).
3. Apply regex in your projects for validation, searching, or data extraction.

## Contributing
Contributions are welcome! Submit pull requests or open issues for suggestions, corrections, or additional examples.

## License
This guide is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

Happy regex-ing!
