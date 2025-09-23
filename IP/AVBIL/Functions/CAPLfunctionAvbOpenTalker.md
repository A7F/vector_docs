# AvbOpenTalker

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `dword AvbOpenTalker();` // form 1
- `dword AvbOpenTalker(dword streamUniqueId);` // form 2
- `dword AvbOpenTalker(byte streamSourceAddress[]);` // form 3
- `dword AvbOpenTalker(byte streamSourceAddress[], dword streamUniqueId);` // form 4

## Description

The function creates a Talker for use in connection-based, message-oriented communications.

## Parameters

- **streamUniqueId**: The stream’s unique identifier.
- **streamSourceAddress**: The stream’s source MAC address (6 byte).

## Return Values

- **0**: The function failed. Call [AvbGetLastError](CAPLfunctionAvbGetLastError.md) to get a more specific error code.
- **Any other value**: A valid Talker handle identifying the created Listener.

## Example

—

[See Also](javascript:void(0);)
