[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILResetBlockedRxMessage.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_ResetBlockedRxMessage

# VTIL_ResetBlockedRxMessage

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_ResetBlockedRxMessage(dword pgn, dword sourceAddress, qword filterMask, qword filterValue); // form 1`
- `long VTIL_ResetBlockedRxMessage(dbNode node, dword pgn, dword sourceAddress, qword filterMask, qword filterValue); // form 2`

## Description

Resets the change of a single [ISO11783VTIL_BlockRxMessage](CAPLfunctionIso11783VTILBlockRxMessage.md) call. The message to unblock is specified by PGN, source address and a part of the first eight data bytes.

## Parameters

- **pgn**: Use same value as in `ISO11783IL_BlockRxMessage` to stop blocking the message.
- **sourceAddress**: Use same value as in `ISO11783IL_BlockRxMessage` to stop blocking the message.
- **filterMask**: Use same value as in `ISO11783IL_BlockRxMessage` to stop blocking the message.
- **filterValue**: Use same value as in `ISO11783IL_BlockRxMessage` to stop blocking the message.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: Blocking has been stopped successfully
- **-1**: There is no matching entry made by `ISO11783IL_BlockRxMessage`
- **-102**: An invalid parameter is used

## Example

—
