[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINResetRespDisturbance.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linResetRespDisturbance

# linResetRespDisturbance

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long linResetRespDisturbance (long frameId);
```

## Description

Deactivates the disturbance in the response space of the specified frame.

## Parameters

- **frameId**: LIN frame identifier in the range 0 .. 63

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linSetRespDisturbance](CAPLfunctionLINSetRespDisturbance.md)
