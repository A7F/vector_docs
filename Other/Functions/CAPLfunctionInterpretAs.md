[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionInterpretAs.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » interpretAsDword, interpretAsFloat, interpretAsQword, interpretAsDouble

# interpretAsDword, interpretAsFloat, interpretAsQword, interpretAsDouble

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `dword interpretAsDword(float x);`
- `float interpretAsFloat(dword x);`
- `qword interpretAsQword(double x);`
- `double interpretAsDouble(qword x);`

## Description

These functions interpret the actual bytes of a value as if the value was of another data type.

**InterpretAsFloat** for example takes the four bytes or a dword, interprets them as if they were four bytes of an IEEE single precision floating point number, and returns that number.

**InterpretAsDouble** interprets eight bytes as if they were an IEEE double precision floating point number.

**InterpretAsDword** and **InterpretAsQword** are the inverse functions.

## Parameters

- **x**: The number which shall be interpreted.

## Return Values

The interpreted value.

## Example

```c
// take a message with 8 bytes representing a double number
on message MessageWithDoubleSignal
{
  qword rawBytes;
  double value;
  rawBytes = this.qword(0);
  value = interpretAsDouble(rawBytes);
  write("The value is %g", value);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
