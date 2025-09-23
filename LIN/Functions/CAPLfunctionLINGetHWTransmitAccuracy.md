[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetHWTransmitAccuracy.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linGetHWTransmitAccuracy

# linGetHWTransmitAccuracy

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
dword linGetHWTransmitAccuracy();
```

## Description

This function can be used to query the transmit resolution of the LIN hardware in units of 1 Hz.

## Parameters

—

## Return Values

Returns the transmit resolution of the LIN hardware.

## Example

```plaintext
on key 't'
{
    write("Transmit accuracy = %d", linGetHWTransmitAccuracy());
    write("Receive  accuracy = %d", linGetHWReceiveAccuracy());
}
```

[linGetHWReceiveAccuracy](CAPLfunctionLINGetHWReceiveAccuracy.md)
