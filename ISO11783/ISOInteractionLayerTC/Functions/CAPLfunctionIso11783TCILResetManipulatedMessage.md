[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILResetManipulatedMessage.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » **TCIL_ResetManipulatedMessage**

# TCIL_ResetManipulatedMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_ResetManipulatedMessage( dword pgn, dword destinationAddress, qword filterMask, qword filterValue ); // form 1
long TCIL_ResetManipulatedMessage( dbNode node, dword pgn, dword destinationAddress, qword filterMask, qword filterValue ); // form 2
```

## Description

Resets the change of a single [ISO11783TCIL_ManipulateMessage](CAPLfunctionIso11783TCILManipulateMessage.md) call. The corresponding message is specified by PGN, destination address and a part of the first eight data bytes.

## Parameters

- **pgn**: Use same value as in `ISO11783TCIL_ManipulateMessage` to stop manipulation of the message.
- **destinationAddress**: Use same value as in `ISO11783TCIL_ManipulateMessage` to stop manipulation of the message.
- **filterMask**: Use same value as in `ISO11783TCIL_ManipulateMessage` to stop manipulation of the message.
- **filterValue**: Use same value as in `ISO11783TCIL_ManipulateMessage` to stop manipulation of the message.
- **node**: Simulation node to apply the function.

## Return Values

- **-1**: There is no matching entry made by `ISO11783TCIL_ManipulateMessage`.
- **-102**: An invalid parameter is used.

## Example

See example of [ISO11783TCIL_ManipulateMessage](CAPLfunctionIso11783TCILManipulateMessage.md).

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
