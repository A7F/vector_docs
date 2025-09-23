# J1939ILResetManipulatedMessage

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILResetManipulatedMessage( dword pgn, dword destinationAddress, qword filterMask, qword filterValue ); // form 1
long J1939ILResetManipulatedMessage( dbNode node, dword pgn, dword destinationAddress, qword filterMask, qword filterValue ); // form 2
```

## Description

Resets the change of a single [J1939ILManipulateMessage](CAPLfunctionJ1939ILManipulateMessage.md) call. The corresponding message is specified by PGN, destination address and a part of the first eight data bytes.

## Parameters

- **pgn**: Use same value as in `J1939ILManipulateMessage` to stop manipulation of the message.
- **destinationAddress**: Use same value as in `J1939ILManipulateMessage` to stop manipulation of the message.
- **filterMask**: Use same value as in `J1939ILManipulateMessage` to stop manipulation of the message.
- **filterValue**: Use same value as in `J1939ILManipulateMessage` to stop manipulation of the message.
- **node**: Simulation node to apply the function.

## Return Values

- **-1**: There is no matching entry made by `J1939ILManipulateMessage`
- **-102**: An invalid parameter is used

## Example

See example of [J1939ILManipulateMessage](CAPLfunctionJ1939ILManipulateMessage.md).
