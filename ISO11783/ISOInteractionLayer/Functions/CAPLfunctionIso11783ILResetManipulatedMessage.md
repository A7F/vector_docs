[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILResetManipulatedMessage.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_ResetManipulatedMessage

# Iso11783IL_ResetManipulatedMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_ResetManipulatedMessage( dword pgn, dword destinationAddress, qword filterMask, qword filterValue ); // form 1
long Iso11783IL_ResetManipulatedMessage( dbNode node, dword pgn, dword destinationAddress, qword filterMask, qword filterValue ); // form 2
```

## Description

Resets the change of a single [ISO11783IL_ManipulateMessage](CAPLfunctionIso11783ILManipulateMessage.md) call. The corresponding message is specified by PGN, destination address and a part of the first eight data bytes.

## Parameters

- **pgn**: Use same value as in [ISO11783IL_ManipulateMessage](CAPLfunctionIso11783ILManipulateMessage.md) to stop manipulation of the message.
- **destinationAddress**: Use same value as in [ISO11783IL_ManipulateMessage](CAPLfunctionIso11783ILManipulateMessage.md) to stop manipulation of the message.
- **filterMask**: Use same value as in [ISO11783IL_ManipulateMessage](CAPLfunctionIso11783ILManipulateMessage.md) to stop manipulation of the message.
- **filterValue**: Use same value as in [ISO11783IL_ManipulateMessage](CAPLfunctionIso11783ILManipulateMessage.md) to stop manipulation of the message.
- **node**: Simulation node to apply the function.

## Return Values

- **-1**: There is no matching entry made by [ISO11783IL_ManipulateMessage](CAPLfunctionIso11783ILManipulateMessage.md)
- **-102**: An invalid parameter is used

## Example

See example of [ISO11783IL_ManipulateMessage](CAPLfunctionIso11783ILManipulateMessage.md).
