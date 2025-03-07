[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStrReplaceRegex.md)

## CAPL Functions » General » Function Overview » str_replace_regex

### str_replace_regex

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

```plaintext
long str_replace_regex(char s[], char pattern[], char replacement[]);
```

### Description

Replaces all occurrences of pattern in a string with another string.

### Parameters

- **s**: String to be modified.
- **pattern**: Regular expression which determines the parts in s which shall be replaced. For the regular expression, the same syntax is used as in the Perl programming language.
- **replacement**: Replacement for the parts which match the pattern.

### Return Values

1 if successful, 0 if the resulting string would be too long for the buffer **s**.

### Example

#### Example 1

```c
char buffer[70] = "Vector Informatik";
str_replace_regex(buffer, "Inf[a-z]*", "CANoe");
write(buffer);
```

#### Note

Some symbols have special meaning in regular expressions and need escaping with backslash to be matched verbatim. These symbols are `.`, `[`, `{`, `}`, `(`, `)`, `\`, `*`, `+`, `?`, `|`, `^`, and `$`. The symbol `]` also needs escaping if it is preceded by a `[` symbol. As regular string literals also use backslash for escaping, there need to be two backslashes to escape a symbol inside a regular expression.

Other symbols can obtain special meaning in regular expressions, if they are escaped with backslash. An example for this would be the character class `d` which can be used to match digits.

#### Example 2

```c
char buffer[8] = "$100.00";
str_replace_regex(buffer, "\\$\\d+.\\d\\d", "100.00€");
write(buffer);
```

[str_match_regex](CAPLfunctionStrMatchRegex.md) • [str_replace](CAPLfunctionStrReplace.md) • [strstr_regex](CAPLfunctionStrstrRegex.md) • [String Literal](../CAPLfunctionsStringLiteral.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)