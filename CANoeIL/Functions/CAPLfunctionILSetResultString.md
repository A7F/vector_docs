# ILSetResultString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ILSetResultString (VILResult aResult, char *aText, long aLenText)
```

## Description

Converts the transferred [error code](../../../CANoeCANalyzer/LibrariesPackages/VectorILCAN/VectorILCANErrorCodes.md) to text.

## Parameters

- **aResult**: Return value of a CANoe IL API function.
- **aText**: Char array.
- **aLenText**: Length of the char array.

## Return Values

- **0**: No error.
- **-103**: Invalid value was passed.

## Example

—

[ILErrno](CAPLfunctionILErrno.md)
