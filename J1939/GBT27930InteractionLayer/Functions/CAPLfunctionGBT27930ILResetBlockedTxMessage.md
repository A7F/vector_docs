[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILResetBlockedTxMessage.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_ResetBlockedTxMessage**

# GBT27930IL_ResetBlockedTxMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_ResetBlockedTxMessage(dword pgn, dword destinationAddress, qword filterMask, qword filterValue); // form 1
long GBT27930IL_ResetBlockedTxMessage(dbNode node, dword pgn, dword destinationAddress, qword filterMask, qword filterValue); // form 2
```

## Description

Resets the change of a single [GBT27930IL_BlockTxMessage](CAPLfunctionGBT27930ILBlockTxMessage.md) call. The message to unblock is specified by PGN, destination address and a part of the first eight data bytes.

## Parameters

- **pgn**: Use same value as in `GBT27930IL_BlockTxMessage` to stop blocking the message.
- **destinationAddress**: Use same value as in `GBT27930IL_BlockTxMessage` to stop blocking the message.
- **filterMask**: Use same value as in `GBT27930IL_BlockTxMessage` to stop blocking the message.
- **filterValue**: Use same value as in `GBT27930IL_BlockTxMessage` to stop blocking the message.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: Blocking has been stopped successfully
- **-1**: There is no matching entry made by `GBT27930IL_BlockTxMessage`
- **-102**: An invalid parameter is used

## Example

—
