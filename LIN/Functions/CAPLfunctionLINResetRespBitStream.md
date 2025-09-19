[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINResetRespBitStream.md)

**CAPL Functions** » **LIN** » linResetRespBitStream

# linResetRespBitStream

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```
long linResetRespBitStream (long frameId);
```

## Description

Deactivates the bitstream response of the specified frame.

## Parameters

- **frameId**: LIN frame identifier in the range 0 .. 63

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linSetRespBitStream](CAPLfunctionLINSetRespBitStream.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
