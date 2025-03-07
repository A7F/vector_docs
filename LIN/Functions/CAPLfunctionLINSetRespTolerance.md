[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetRespTolerance.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetRespTolerance

# linSetRespTolerance

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
dword linSetRespTolerance(long frameId, long toleranceInPercent);
```

## Description

Sets the response tolerance for a specified frame in percent.

## Parameters

- **frameId**  
  The identifier of the frame for which the response tolerance shall be set.

- **toleranceInPercent**  
  The response tolerance to be used for the specified frame.  
  Value range: 0-255

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linResetMaxHeaderLength](CAPLfunctionLINResetMaxHeaderLength.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)