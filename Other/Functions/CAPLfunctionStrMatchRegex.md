[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStrMatchRegex.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » str_match_regex

# str_match_regex

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long str_match_regex(char s[], char pattern[]);
```

## Description

Checks whether a string completely matches a regular expression pattern.

## Parameters

- **s**: String to be checked.
- **pattern**: Regular expression against which the string is matched. For the regular expression, the same syntax is used as in the Perl programming language.

## Return Values

1 if the string matches the pattern, 0 if it doesn’t match the pattern.

## Example

**Example 1**

```plaintext
char buffer[70] = "Vector Informatik";
long res;
res = str_match_regex(buffer, "Vector [A-Za-z]*"); // 1
res = str_match_regex(buffer, "Inf[a-z]*"); // 0
```

**Note**

Some symbols have special meaning in regular expressions and need escaping with backslash to be matched verbatim. These symbols are `.`, `[`, `{`, `}`, `(`, `)`, `\`, `*`, `+`, `?`, `|`, `^`, and `$`. The symbol `]` also needs escaping if it is preceded by a `[` symbol. As regular string literals also use backslash for escaping, there need to be two backslashes to escape a symbol inside a regular expression.

Other symbols can obtain special meaning in regular expressions, if they are escaped with backslash. An example for this would be the character class `d` which can be used to match digits.

**Example 2**

```plaintext
char buffer[8] = "$100.00";
long res;
res = str_match_regex(buffer, "\\$\\d+\\.\\d\\d"); // 1
```

[str_replace](CAPLfunctionStrReplace.md) • [str_replace_regex](CAPLfunctionStrReplaceRegex.md) • [strstr_regex](CAPLfunctionStrstrRegex.md) • [String Literal](../CAPLfunctionsStringLiteral.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
