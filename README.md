# Regex Tutorial : matching an Email

Regex is a short for regular expression. When someone sees the Regex pattern at first, it may seem to look like a cryptic expressions. However, things change as soon as people start to understand how versatile and helpful the Regex can be when it is being used to define a specific search pattern.
Formally Regex is defined as the expression to be used to find pattenrs of characters within a string, find and replace a character or sequence of characters within a string, or to validate an input if it is a string.

## Summary

This tutorial is aimed to describe one of the most commonly required expressions - matching an Email, which the author of this manual has been able to use a couple of times in the code while he was writing that manual.
Regex is considered a literal, so the pattern must be wrapped in slash characters (/). For matching correctly entered Email following should be true:

/^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/

JavaScript has many useful methods which can be used with RegExp and String: 
Regular expressions are used with the RegExp methods test() and exec() and with the String methods match(), replace(), search(), and split().
Formal definitions and examples can be looked up at [MDN Web Docs](#https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions).

## Table of Contents

- [Regex Components](#Regex%20Components)
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

Regular expressions contain:
- Single characters with no special significance just represents that character in a target string, the characters with the special significance are these: ^ . [ $ ( ) | * + ? { \ If there is a need to include the special significance character in the target string there is a way to ESCAPE it adding backslash \ before that chararcter, 
- Wild cards (*, . symbols), 
- Bracket Expressions (character sets enclosed by square brackets [ ]),
- Control characters (a backslash \ followed by one of the characters a,b,f,n,r,t,v which represent ANSI-C interpretation of control character), 
- Escape character sets (\w is word [A-Za-z0-9], \W is non-word [^A-Za-z0-9], \s is whitespace [ \f\n\r\t], \S is non-whitespace [^ \f\n\r\t], \d is digit [0-9], \D is non-digit [^0-9]),
- Anchors are the special sequences which match an empty string: ^ matches at the beginning of a target string, $ matches at the end of target string, \b matches on a word boundary, i.e. previous or subsequent character is not a word character,
- Recursive expansion: any regular expression surrounded by parentheses is an atom: { regular_expression }

### Anchors

The characters ^ and $ are both considered to be anchors. So the RegEx starts with /^ and finishes with $/


### Quantifiers

Quantifiers set the limits of the string or individual section of the string the regex matches. They can include the minimum and maximum number of characters that regex is looking for.

Quantifiers match as many occurences of particular patterns as possible.

They include the following:

* - matches the pattern zero or more times
+ - matches the pattern one or more times
? - matches the pattern zero or one time
{} - provide three different ways to set limits for a match:
  { n } - matches the pattern exactly n number of times
  { n, } - matches the pattern at least n number of times
  { n, x } - matches the pattern from minimum n number of times to maximum x number of times.
In our correct e-mail regex:
/^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/

[\w-]{2,4} quantifier means that the word \w which could contain a-z,A-Z,0-9 and - symbol can be between 2 and 4 characters.

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

Regular expressions allow to not only match text but also to extract information for further processing. This is done by defining groups of characters and capturing them using the special parentheses ( and ) metacharacters. Any subpattern inside a pair of parentheses will be captured as a group. In practice, this can be used to extract information like phone numbers or emails from all sorts of data.

In our e-mail regex /^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/  we use ([\w-]+\.) to define the domain name of the e-mail address which would be finished by the dot before the country code which is defined in [\w-]{2,4} 


### Bracket Expressions

Anything inside of the squre brackets ([]) represents a range of characters that we want to match. These patterns are known as bracket expressions or otherwise positive character group if we want to match it. There is a way to include ^ symbol in bracket expression, which would mean that we do not want ti include anything that matches that character sequence.
For example, in our e-mail matching RegEx
/^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/
we have following bracket expressions which we would like any candidate string to match:
[\w-\.]
[\w-]
If a hyphen (-) used between the alphanumeric characters (letters and numbers), that would represent a range of the possible candidates, for example [a-z] is looking for a string containing any lower case letters from a to z. 

### Greedy and Lazy Match

Greedy search: to find a match, the regular expression engine uses the following algorithm:
- For every position in the string;
- Try to match the pattern at that position;
- If there’s no match, go to the next position;

The lazy mode of quantifiers is an opposite to the greedy mode. It means: “repeat minimal number of times”.
Laziness is only enabled for the quantifier with ?.
Other quantifiers remain greedy.

### Boundaries

The word boundary \b matches positions where one side is a word character (usually a letter, digit or underscore) and the other side is not a word character (for instance, it may be the beginning of the string or a space character).

Not-a-word-boundary: \B
\B matches all positions where \b doesn't match. 

### Back-references

### Look-ahead and Look-behind

## Author

My GitHub name is vl1. Most of the answers to the questions can be found there, here is the link to my profile at GitHub:

  https://github.com/vl1

  For additional questions please e-mail to likhovaido@gmail.com

  Thank you for your interest in this manual.