[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionAtodbl.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » atodbl

# atodbl

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
double atodbl(char s[]);
```

## Description

The function converts the string s into a double number. Normally, the base is decimal and must have the following format:

[Blank space] [Sign] [Digits] [.Digits] [ {d | D | e | E}[Sign]Digits]

String parsing ceases at the first non-compliant character.

If the string cannot be converted into a number, 0.0 is returned.

If the string starts with 0x, the base used is 16. Only integer numbers can be read in.

## Parameters

Input string to be converted.

## Return Values

Double number, the converted string.

## Example

```plaintext
double d;
d = atodbl(" -3.7");     // -3.7
d = atodbl("0x1F");      // 31.0
d = atodbl("1.3E2");     // 130.0
```

[atol](CAPLfunctionAtol.md) • [strtod](CAPLfunctionStrtod.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
