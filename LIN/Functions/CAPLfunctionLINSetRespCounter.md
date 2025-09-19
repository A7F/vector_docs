[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetRespCounter.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetRespCounter

# linSetRespCounter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long linSetRespCounter(long frameID, long count);
```

## Description

With this function, it is possible to limit the number of responses sent for the specified frame identifier.

- By setting `count = 0`, it is possible to deactivate the frame response completely.
- With `count = -1`, a frame response is always sent when a correct frame header is received. This is the default configuration for newly configured frames.

## Parameters

- **frameID**: Identifier of the LIN frame to be configured  
  Value range: 0…63

- **count**: Number of responses to be sent.  
  n-times: 0..254  
  unlimited: -1

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linActivateResps](CAPLfunctionLINActivateResps.md) • [linDeactivateResps](CAPLfunctionLINDeactivateResps.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
