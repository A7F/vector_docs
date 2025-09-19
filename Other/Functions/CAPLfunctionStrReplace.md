[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStrReplace.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » str_replace

# str_replace

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long str_replace(char s[], char searched[], char replacement[]); // form 1`
- `long str_replace(char s[], long startoffset, char replacement[], long length); // form 2`

## Description

- **Form 1:** Replaces all occurrences of a text in a string with another string.
- **Form 2:** Replaces a part of a string with another string.

## Parameters

- **s**: String to be modified.
- **searched**: Text which shall be replaced.
- **startoffset**: Offset at which to start replacing characters.
- **replacement**: Text which replaces the original characters.
- **length**: Maximum number of characters to replace.

## Return Values

1 if successful, 0 if the resulting string would be too long for the buffer **s**.

## Example

```c
char buffer[70] = "Vector Informatik";
str_replace(buffer, "Informatik", "CANoe");
write(buffer);
str_replace(buffer, 7, "CANalyzer", 10);
write(buffer);
```

[str_match_regex](CAPLfunctionStrMatchRegex.md) • [str_replace_regex](CAPLfunctionStrReplaceRegex.md) • [strstr_regex](CAPLfunctionStrstrRegex.md) • [String Literal](../CAPLfunctionsStringLiteral.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
