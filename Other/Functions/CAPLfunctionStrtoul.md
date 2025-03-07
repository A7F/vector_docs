[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStrtoul.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » strtoul

# strtoul

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
int strtoul(char s[], dword& result); // from 1
int strtoul(char s[], dword startIndex, dword& result); // from 2
```

## Description

Converts the string **s** to an unsigned 32bit integer. The number base is:

- hexadecimal if the string starts with ‘0x’
- octal if it starts with ‘0’
- decimal otherwise

Whitespace (spaces or tabs) at the start of the string is ignored.

## Parameters

- **s**: String to be converted.
- **result**: Contains the converted value after the call. The value is 0 if the string can’t be converted to a number. It is the largest possible positive/negative number in case of overflow.
- **startIndex**: Position in s where the conversion shall begin.

## Return Values

- **-2**: If **s** is empty or **startIndex** is larger than [strlen(s)](CAPLfunctionStrLen.md).
- **-1**: An overflow occurs.

Otherwise, returns the index of the first character after the number.

## Example

```plaintext
char s[20] = "123 0xFF";
dword number1, number2;
int res;
res = strtoul(s, number1);
write("number1: %u, res: %d", number1, res); // output: number1: 123, res: 3
res = strtoul(s, res, number2);
write("number2: %u, res: %d", number2, res); // output: number2: 255, res: 8
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)