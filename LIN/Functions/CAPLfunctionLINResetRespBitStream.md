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
