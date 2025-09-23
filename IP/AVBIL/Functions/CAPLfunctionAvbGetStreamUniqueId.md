# AvbGetStreamUniqueId

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AvbGetStreamUniqueId(dword listenerOrTalkerHandle, dword& retStreamUniqueId);
```

## Description

The function retrieves the stream’s Unique Identifier (ID) of the Listener or Talker as part of the Stream Identifier (ID).

## Parameters

- **listenerOrTalkerHandle**: The handle of the Listener or Talker.
- **retStreamUniqueId**: The 16 bitstream Unique Identifier (ID) upon successful return of the function.

## Return Values

- **0**: The function completed successfully.
- **>0**: [Error code](../CAPLfunctionsAVBILErrorCode.md)

## Example

—

[See Also](javascript:void(0);)
