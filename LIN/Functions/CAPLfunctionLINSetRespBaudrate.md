[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetRespBaudrate.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetRespBaudrate

# linSetRespBaudrate

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long linSetRespBaudrate(long frameId, long baudrate);
```

## Description

Sets a response baudrate for a specified frame. This baudrate will be used for the response, regardless of the master baudrate.

## Parameters

- **frameId**: The identifier of the frame for which the response baudrate will be set.
- **baudrate**: The baudrate to be used for the response.  
  Value range: 1000-20000

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linResetRespBaudrate](CAPLfunctionLINResetRespBaudrate.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)