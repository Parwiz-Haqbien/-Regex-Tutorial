#  Regular Expression Match a Hex Value

This file is intended to describe the details about specific regular expression, in this example we will be analyzing Hex value. The description 
is going to be down below and how it works

## Summary
 We will be analysing the following regular expresion used to match the Hex Values:
 
  /^#?([a-f0-9]{6}|[a-f0-9]{3})$/
  
  Description below will provide details of the anchors, quantifiers, OR Operator, grouping and capturing and bracket expressions used in this regular expression.


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors
^ code snipe: /^#

Descriptions:

The ^ anchor signifies a string that begins with the characters that follow it. This could be in one of two formats:

An exact string match, such as ^The, where the strings "The" or "The person" match, but "the" and "the person" do not. This is because a regex is case-sensitive.

#: symbol is used to represent the start and end of a comment. Anything after a # symbol in a regular expression will be ignored by the regex engine, so it's often used to add notes or explanations within the regex itself to make it more readable

Anhor $:

code snipe: $/

In regular expressions, the $ symbol is used to match the end of a string. For example, the regular expression /cat$/ would match any string that ends with the word "cat", such as "The cat sat on the mat" or "I like cats".

In our case end of string must match with the 3 or 6 character pattern identified before the $ anchor. The 3 or 6 character pattern is described in more detail under Quantifiers.
### Quantifiers

Quantifier: ?

code snipe : /^#?

Description:

The ? symbol is used to match zero or one occurrence of the preceding character or group. For example, the regular expression /ab?c/ would match strings like "ac", "abc", and "abbc" but not "abcc" or "abbcc"

Quantifier: {}

code snipe: [a-f0-9]{6} code snipe: [a-f0-9]{3}

Description:

the {} symbols are used to specify a repetition interval. The interval specifies the minimum and maximum number of times that the preceding character or group can be repeated in a string. For example, the regular expression /\d{3,5}/ would match any string that contains a sequence of at least three and at most five digits.

Example: 2{4} means 2 must be repated 4 times, the results should like 2222

In our regix: 

The {6} syntax specifies that the preceding character or group must be repeated exactly six times in a string. For example, the regular expression /\d{6}/ would match any string that contains exactly six digits, such as "123456" or "987654".
### OR Operator

OR Operator: |

code snipe: [a-f0-9]{6}|[a-f0-9]

Description: 

The | symbol is used to match one of several possible patterns. It is often called a "pipe" or "or" symbol, and it is used to separate multiple alternatives in a regular expression. For example, the regular expression /cat|dog|fish/ would match any string that contains the word "cat", the word "dog", or the word "fish".

In our regix :
| means to match with 3 character string containing lower case a-f and/or integer 0-9 OR a string with 6 characters containing lowercase a-f and/or integer between 0-9. A matching string has to have 3 or 6 character with the specified pattern. Anything other than 3 or 6 characters will not match
### Character Classes
  
code snipe: a-f0-9

Description:

the a-f0-9 syntax is used to match any single character in the range "a" through "f" or "0" through "9". It is called a character class, and it is used to match any character that belongs to a specific set of characters. For example, the regular expression /[a-f0-9]/ would match any string that contains a single character that is either a letter between "a" and "f" or a digit between "0" and "9".

In our case:

The character class consists of lower case a-f and/or integer 0-9

### Grouping and Capturing

Grouping and Capturing: ()

Code Snipet: ([a-f0-9]{6}|[a-f0-9]{3})

Description:

The () symbols are used to create a capture group. A capture group is a section of a regular expression that is enclosed in parentheses, and it allows you to extract specific parts of the string that matches the regex. For example, the regular expression /(\d{3})-(\d{3})-(\d{4})/ would match a phone number in the format "###-###-####" and capture the area code, exchange code, and subscriber number as separate groups.

### Bracket Expressions

Bracket Expression: []

Code Snipet: [a-f0-9]

Description:

The [] symbols are used to create a character class. A character class is a set of characters that you want to match in a string. For example, the regular expression /[aeiou]/ would match any string that contains a single vowel.

In our case:

Matching a string that has any lower case character between a-f or any integer between 0-9

### Greedy and Lazy Match

Code Snipet: [a-f0-9]{6} Code Snipet: [a-f0-9]{3}

Quantifier: {}

Description:

Description: Greedy means match the longest possible string. Lazy means match the shortest possible string.

Example: w.+l matches well in well but the lazy w.+?l matches wel

The explaination of {} is explained in Quantifier


## Author

My name is Parwiz Haqbien and my main objective with the bootcamp and in general is to learn to front and backend which includes CSS, JavaScript
, HTML, Nodejs, MySql and list go on.

GitHub: https://github.com/Parwiz-Haqbien
