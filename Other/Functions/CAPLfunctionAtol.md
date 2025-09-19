[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionAtol.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » atol

# atol

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long atol(char s[]);
```

## Description

Converts the string **s** to a LONG number. The number base is decimal. Starting with string 0x, base 16 is used. Leading blanks are not read.

## Parameters

- **s**: String to be converted.

## Return Values

- The converted number.
- 0 will be returned if the string is no number.

## Example

```plaintext
...
long z1;
long z2;
z1 = atol("200");
z2 = atol("0xFF");
...
```

Result:  
z1 = 200, z2 = 255

[ltoa](CAPLfunctionltoa.md) • [strtol](CAPLfunctionStrtol.md) • [strtoul](CAPLfunctionStrtoul.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
