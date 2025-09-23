[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetBusIdleTimeout.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linGetBusIdleTimeout

# linGetBusIdleTimeout

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword linGetBusIdleTimeout();
```

## Description

This function returns the currently set bus idle timeout. Depending on the protocol version, the timeout will be specified in bit times (LIN 1.x and Cooling) or in milliseconds (all others).

## Parameters

—

## Return Values

On success, returns the bus idle timeout, otherwise zero.

## Example

—

[linSetBusIdleTimeout](CAPLfunctionLINSetBusIdleTimeout.md)
