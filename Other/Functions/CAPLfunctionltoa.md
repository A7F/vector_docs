[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionltoa.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » ltoa

# ltoa

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void ltoa(long val, char s[], long base);
```

## Description

The number **val** is converted to a string **s**. In this case, **base** indicates a number base between 2 and 36. s must be large enough to accept the converted number!

## Parameters

- **val**: Number to be converted.
- **s**: String, which contains the converted number.
- **base**: Number base.

## Return Values

—

## Example

```plaintext
char s1[9];
char s2[9];
ltoa(z,s1,2);
ltoa(z,s2,10);
write("z: %d s1= %s",z, s1);
write("z: %d s2= %s",z, s2);
...
```

Result:

```plaintext
z: 255 s1= 11111111
z: 255 s2= 255
```

[atol](CAPLfunctionAtol.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
