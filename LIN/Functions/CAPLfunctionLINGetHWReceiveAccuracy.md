[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetHWReceiveAccuracy.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linGetHWReceiveAccuracy

# linGetHWReceiveAccuracy

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword linGetHWReceiveAccuracy();
```

## Description

This function can be used to query the receive resolution of the LIN hardware in units of 1 Hz.

## Parameters

—

## Return Values

Returns the receive resolution of the LIN hardware.

## Example

```c
on key 't'
{
    write("Transmit accuracy = %d", linGetHWTransmitAccuracy());
    write("Receive  accuracy = %d", linGetHWReceiveAccuracy());
}
```

[linGetHWTransmitAccuracy](CAPLfunctionLINGetHWTransmitAccuracy.md)
