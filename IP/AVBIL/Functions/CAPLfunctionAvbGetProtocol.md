# AvbGetProtocol

[Valid for: CANoe DE • CANoe4SW DE](../../../../Shared/FeatureAvailability.md)

## Function Syntax

```
dword AvbGetProtocol(dword listenerOrTalkerHandle, dword& retProtocol);
```

## Description

The function retrieves the AVTP protocol of the Listener or Talker.

## Parameters

- **listenerOrTalkerHandle**: The handle of the Listener or Talker.
- **retProtocol**: The AVTP protocol upon successful return of the function. The currently supported protocols are:
  - **0x02**: AAF (AVTP Audio Format)
  - **0x04**: CRF (Clock Reference Format)

  When **RTP** is used, this function returns an error.

## Return Values

- **0**: The function completed successfully.
- **>0**: [Error code](../CAPLfunctionsAVBILErrorCode.md)

## Example

—

[See Also](javascript:void(0);)
