[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILSetResultString.md)

**CAPL Functions** » **CANoe IL** » **ILSetResultString**

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)