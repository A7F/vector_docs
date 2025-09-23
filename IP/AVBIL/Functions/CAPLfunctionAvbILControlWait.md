# AvbILControlWait

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AvbILControlWait();
```

## Description

Stops sending AVB/TSN related messages.

Open Talkers and Listeners are not closed and the time aware end station (PTP clock instance) continues to run. Stream content continues to be received by the AVB IL and can be evaluated. Talkers suppress their automatic stream perpetuation which means they do not fill gaps by sending zero samples when no AvbSend calls are made through CAPL.

Use [AvbILControlResume](CAPLfunctionAvbILControlResume.md) to enable message sending behavior again.

## Parameters

—

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../CAPLfunctionsAVBILErrorCode.md)

## Example

—

[See Also](javascript:void(0);)
