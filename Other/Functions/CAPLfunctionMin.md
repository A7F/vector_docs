[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionMin.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » _min

# _min

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long _min(long x, long y); // form 1`
- `dword _min(dword x, dword y); // form 2`
- `int64 _min(int64 x, int64 y); // form 3`
- `qword _min(qword x, qword y); // form 4`
- `float _min(float x, float y); // form 5`

## Description

Returns the minimum of the parameters.

## Parameters

- **x**: First operand
- **y**: Second operand

## Return Values

- **y < x ? y**: x

## Example

```c
float result;
result = _min(1.0, _min(-3.0, 5.2)); // result == -3.0
```
