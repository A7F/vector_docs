[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILResetManipulatedMessage.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_ResetManipulatedMessage**

# VTIL_ResetManipulatedMessage

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long VTIL_ResetManipulatedMessage( dword pgn, dword destinationAddress, qword filterMask, qword filterValue ); // form 1
long VTIL_ResetManipulatedMessage( dbNode node, dword pgn, dword destinationAddress, qword filterMask, qword filterValue ); // form 2
```

## Description

Resets the change of a single [ISO11783VTIL_ManipulateMessage](CAPLfunctionIso11783VTILManipulateMessage.md) call. The corresponding message is specified by PGN, destination address, and a part of the first eight data bytes.

## Parameters

- **pgn**: Use same value as in `ISO11783VTIL_ManipulateMessage` to stop manipulation of the message.
- **destinationAddress**: Use same value as in `ISO11783VTIL_ManipulateMessage` to stop manipulation of the message.
- **filterMask**: Use same value as in `ISO11783VTIL_ManipulateMessage` to stop manipulation of the message.
- **filterValue**: Use same value as in `ISO11783VTIL_ManipulateMessage` to stop manipulation of the message.
- **node**: Simulation node to apply the function.

## Return Values

- **-1**: There is no matching entry made by `ISO11783VTIL_ManipulateMessage`.
- **-102**: An invalid parameter is used.

## Example

See example of [ISO11783VTIL_ManipulateMessage](CAPLfunctionIso11783VTILManipulateMessage.md).

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)