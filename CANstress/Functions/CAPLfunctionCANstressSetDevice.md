# CANstressSetDevice

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long CANstressSetDevice (dword deviceId);
```

## Description

Defines the active device for further functions.

## Parameters

- **deviceId**: Handle for the CANstress device on which further functions are to run. This handle is sent back by the [CANstressCreateServer](CAPLfunctionCANstressCreateServer.md) function.

## Return Values

- **0**: If successful.
- **-1**: In case of error. This means that **deviceId** is not a valid handle for a CANstress device. Only handles sent back by the [CANstressCreateServer](CAPLfunctionCANstressCreateServer.md) function and for which the connection to the COM server has not yet been terminated with [CANstressQuit](CAPLfunctionCANstressQuit.md) are valid.

## Example

—
