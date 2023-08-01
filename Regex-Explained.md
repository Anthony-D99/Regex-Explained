# Regex-Explained

The following tutorial will help users better understand how a regular expression works using the example of verifying a users email. The tutorial will go through each step of the process and provide examples of what will and won't be accepted by the expression.

## Summary

Matching an Email: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
The code snippet that is displayed above is the regular expression that will be covered in this tutorial. This expression can be used by coders to check if a users email input matches the standerd format for an acceptable email address. The tutorial will breach down each part of the regular expression to help the reader better understand what each component does and what it is allowing the user to include in order for the email to be deemed acceptable.
## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors
There are two anchors that are included in a regular expression, the '^' key, and the '$'. The '^' key will always be found at the beginning of the expression following the opening '/'. The '^' key is there to signify that the following components are to be considered as a string. A string in regular terms is another word for text. The '$' can always be found at the end of the regular expression. The '$' key signifies the end of the string that comes before it thus enclosing the regular expression that was opened with the '^' key.
### Quantifiers
Quantifiers are included in the regular expression to set limits to the string that the regular expression is matching with. More often you will see them used to allow a minimum and maximum number of characters that the regular expression is looking for. Some examples of quantifiers includes:
 *—Matches the pattern zero or more times;
 +—Matches the pattern one or more times;
 ?—Matches the pattern zero or one time;
 {}—Curly brackets can provide three different ways to set limits for a match:
    { n }—Matches the pattern exactly n number of times;
    { n, }—Matches the pattern at least n number of times;
    { n, x }—Matches the pattern from a minimum of n number of times to a maximum of x number of times;

You can see a quantifier being used in our example regular expression at the end '{2,6}'. This quantifier allows the string to include a minimum of 2 characters and a maximum of 6 characters. In our example the '{2,6}' is only included in the last perenthesis '\.([a-z\.]{2,6})' (refer to "Grouping Constructs" for more info). What this means is that following the '.' the string can only included 2-6 characters.
Correct Ending: '.com' (string included lowercase letters and is withing the 2-6 character limit.)
Invalid Ending: '.c0mMercial' (invalid string, cannot include numbers, uppercase letters, and is more than 6 characters.)
### Grouping Constructs
Group constructs can be used in a regular expression to break down the string in to sections. Since we are verifying an email in our example expression grouping constructs are very useful. In our example we have three different grouping constructs '([a-z0-9_\.-]+)', '([\da-z\.-]+)', '([a-z\.]{2,6})'. Each have their own rules set out and are kept separate to ensure that the regular expression has the proper outline for a valid email.
### Bracket Expressions
Bracket Expressions are used to represent a range of characters that is need to be matched with. In our example we have three seperate instances of bracket expressions. In the first bracket '[a-z0-9_\.-]' we have a few different rules set. The string must only include lowercase letters from a-z, numbers from 0-9, '_', '.', and '-' with no limit to the number of characters allowed. An example of a valid string would be "av_dyt.8b-1". An example of an invalid string would be "AC%$#@()". 

In the following bracket we are introduced to something different '[\da-z\.-]'. The '\d' that starts the expression is a metacharacter that is used to represent any digit 0-9, we can also see similar to the last bracket that lower case letter a-z,'.', and '-' are valid characters. An example of a valid string for this expression would be "6xa.ar-". An example of an invalid string woud be "$ARF(#)". 

The final bracket '[a-z\.]' includes no new rules or metacharacters and simply checks for lowercase letter from a-z, and '.'. An example of a valid string would be ".net". An example of an invalid string would be "%COM)@".
### Character Classes
Character classes in a regular expression can be used to define a certain set of characters. The most common character classes 
include:
.—Matches any character except the newline character (\n);

\d—Matches any Arabic numeral digit. This class is equivalent to the bracket expression [0-9].;

\w—Matches any alphanumeric character from the basic Latin alphabet, including the underscore (_). This class is equivalent to the bracket expression [A-Za-z0-9_].;

\s—Matches a single whitespace character, including tabs and line breaks;

### Character Escapes
Character Escapes in a regular expression are used to define wether a character should or should not be included in the string being checked.
The '\' key can be used to escape a character that the expression would otherwise interpret literally. In our example we can see it being used in every bracket expression as '\.'. This allows for the expression to include '.' when it would otherwise be interpreted literally. 
## Author

https://github.com/Anthony-D99
