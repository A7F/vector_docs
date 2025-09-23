# AvbOpenListener

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword AvbOpenListener(); // form 1`
- `dword AvbOpenListener(dword streamUniqueId); // form 2`
- `dword AvbOpenListener(byte streamSourceAddress[]); // form 3`
- `dword AvbOpenListener(byte streamSourceAddress[], dword streamUniqueId); // form 4`

## Description

The function creates a Listener for use in connection-based, message-oriented communications.

## Parameters

- **streamUniqueId**: The stream’s unique identifier.
- **streamSourceAddress**: The stream’s source MAC address (48 bit).

## Return Values

- **0**: The function failed. Call [AvbGetLastError](CAPLfunctionAvbGetLastError.md) to get a more specific error code.
- **Any other value**: A valid Listener handle identifying the created Listener.

## Example

—

[See Also](javascript:void(0);)
