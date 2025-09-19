[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetMaxHeaderLength.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetMaxHeaderLength

# linSetMaxHeaderLength

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword linSetMaxHeaderLength(long bitTimes);
```

## Description

Sets the maximum header length in bit times.

## Parameters

- **bitTimes**: The new maximum header length in bit times. Headers longer than the maximum header length will be considered illegal. CANoe will not generate any response to these headers.  
  Value range: 31-255

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linResetMaxHeaderLength](CAPLfunctionLINResetMaxHeaderLength.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
