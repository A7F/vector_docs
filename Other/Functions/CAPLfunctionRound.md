[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionRound.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » _round

# _round

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long _round(double x); // form 1
int64 _round64(double x); // from 2
```

## Description

Rounds x to the nearest integral number. The rounding method used is symmetric arithmetic rounding.

## Parameters

- **x**: Number to be rounded

## Return Values

- Nearest integral number.
- For very large numbers, you should use _round64, which returns a 64 bit integer.

## Example

```plaintext
long result;
result = _round(2.4); // result == 2
result = _round(2.5); // result == 3
result = _round(-3.5); // result == -4
```

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
