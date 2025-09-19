[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionMax.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » _max

# _max

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long _max(long x, long y); // form 1`
- `dword _max(dword x, dword y); // form 2`
- `int64 _max(int64 x, int64 y); // form 3`
- `qword _max(qword x, qword y); // form 4`
- `float _max(float x, float y); // form 5`

## Description

Returns the maximum of the parameters.

## Parameters

- **x**: First operand
- **y**: Second operand

## Return Values

- **y > x ? y**: x

## Example

```c
float result;
result = _max(1.0, _max(-3.0, 5.2)); // result == 5.2
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
