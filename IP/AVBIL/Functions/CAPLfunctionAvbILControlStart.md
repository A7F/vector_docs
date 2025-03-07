[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionAvbILControlStart.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [AVB IL](../CAPLfunctionsAVBILOverview.md) » AvbILControlStart

# AvbILControlStart

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AvbILControlStart();
```

## Description

Starts the AVB IL.

Enables sending and receiving of AVB/TSN related messages. After the start of the AVB IL, the time aware end station (PTP clock instance) starts up and Talkers and/or Listeners can be created.

The AVB IL can be stopped using the [AvbILControlStop](CAPLfunctionAvbILControlStop.md) function.

## Parameters

—

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../CAPLfunctionsAVBILErrorCode.md)

## Example

—

[See Also](javascript:void(0);)