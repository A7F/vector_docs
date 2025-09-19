[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStrstrRegex.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » strstr_regex, strstr_regex_off

# strstr_regex, strstr_regex_off

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long strstr_regex(char s[], char pattern[]);
long strstr_regex_off(char s[], long offset, char pattern[]);
```

## Description

Searches for a regular expression pattern in a string.

## Parameters

- **s**: String to be searched.
- **offset**: Offset in s at which the search shall be started.
- **pattern**: Regular expression which is searched. For the regular expression, the same syntax is used as in the Perl programming language.

## Return Values

The position in s where the pattern was found, or -1 if it wasn’t found.

## Example

**Example 1**

```c
char buffer[70] = "Vector Informatik";
long res;
res = strstr_regex(buffer, "Inf[a-z]*"); // 7
res = strstr_regex_off(buffer, res + 1, "Inf[a-z]*"); // -1
```

**Note**

Some symbols have special meaning in regular expressions and need escaping with backslash to be matched verbatim. These symbols are `.`, `[`, `{`, `}`, `(`, `)`, `\`, `*`, `+`, `?`, `|`, `^`, and `$`. The symbol `]` also needs escaping if it is preceded by a `[` symbol. As regular string literals also use backslash for escaping, there need to be two backslashes to escape a symbol inside a regular expression.

Other symbols can obtain special meaning in regular expressions, if they are escaped with backslash. An example for this would be the character class `d` which can be used to match digits.

**Example 2**

```c
char buffer[8] = "$100.00";
long res;
res = strstr_regex(buffer, "\\$\\d+\\.\\d\\d"); // 0
```

[str_match_regex](CAPLfunctionStrMatchRegex.md) • [str_replace](CAPLfunctionStrReplace.md) • [str_replace_regex](CAPLfunctionStrReplaceRegex.md) • [String Literal](../CAPLfunctionsStringLiteral.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
