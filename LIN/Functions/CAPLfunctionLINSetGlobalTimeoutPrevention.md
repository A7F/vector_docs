[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetGlobalTimeoutPrevention.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetGlobalTimeoutPrevention

# linSetGlobalTimeoutPrevention

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword linSetGlobalTimeoutPrevention(dword on);
```

## Description

Activates/deactivates the global timeout prevention for transceivers with a dominant timeout. If active, the cab/piggy will use an inbuilt transistor to keep the bus signal at a dominant level after the dominant timeout stopped the transceiver from transmitting a dominant signal.

## Parameters

- **on**
  - 0: Disable
  - 1: Enable

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linGetDominantTimeout](CAPLfunctionLINGetDominantTimeout.md)
