[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStrtod.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » strtod

# strtod

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `int strtod(char s[], double& result);` // form 1
- `int strtod(char s[], dword startIndex, double& result);` // form 2

## Description

Converts the string **s** to a floating point number. The string must have the format `[whitespace][sign][digits][.digits][{d|D|e|E}[sign]digits]`.

- **Whitespace**: may consist of space and tab characters, which are ignored
- **sign**: is either plus (+) or minus (-)
- **digits**: are one or more decimal digits. If no digits appear before the radix character, at least one must appear after the radix character. The decimal digits can be followed by an exponent, which consists of an introductory letter (d, D, e, or E) and an optionally signed integer. If neither an exponent part nor a radix character appears, a radix character is assumed to follow the last digit in the string.

## Parameters

- **s**: String to be converted.
- **result**: Contains the converted value after the call. The value is 0 if the string can’t be converted to a number. It is the largest possible positive/negative number in case of overflow.
- **startIndex**: Position in s where the conversion shall begin.

## Return Values

- **-2**: If **s** is empty or **startIndex** is larger than [strlen(s)](CAPLfunctionStrLen.md).
- **-1**: An overflow occurs.

Otherwise, returns the index of the first character after the number.

## Example

```c
char s[20] = "-1.23 2.4E3";
double number1, number2;
int res;
res = strtod(s, number1);
write("number1: %g, res: %d", number1, res); // output: number1: -1.23, res: 5
res = strtod(s, res, number2);
write("number2: %g, res: %d", number2, res); // output: number2: 2400, res: 11
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
