[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionAvbILControlStop.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **AvbILControlStop**

# AvbILControlStop

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AvbILControlStop();
```

## Description

Stops the AVB IL.

Disables sending and receiving of AVB/TSN related messages. Opened Talkers and Listeners are closed, and the associated handles become invalid.

Handles obtained via the Media API stay valid.

The AVB IL can be started again using the [AvbILControlStart](CAPLfunctionAvbILControlStart.md) function.

## Parameters

—

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../CAPLfunctionsAVBILErrorCode.md)

## Example

—

[See Also](javascript:void(0);)
