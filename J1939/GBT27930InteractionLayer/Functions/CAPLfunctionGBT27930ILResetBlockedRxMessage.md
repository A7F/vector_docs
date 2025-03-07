[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILResetBlockedRxMessage.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_ResetBlockedRxMessage**

# GBT27930IL_ResetBlockedRxMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_ResetBlockedRxMessage(dword pgn, dword sourceAddress, qword filterMask, qword filterValue); // form 1
long GBT27930IL_ResetBlockedRxMessage(dbNode node, dword pgn, dword sourceAddress, qword filterMask, qword filterValue); // form 2
```

## Description

Resets the change of a single [GBT27930IL_BlockRxMessage](CAPLfunctionGBT27930ILBlockRxMessage.md) call. The message to unblock is specified by PGN, source address and a part of the first eight data bytes.

## Parameters

- **pgn**: Use same value as in `GBT27930IL_BlockRxMessage` to stop blocking the message.
- **sourceAddress**: Use same value as in `GBT27930IL_BlockRxMessage` to stop blocking the message.
- **filterMask**: Use same value as in `GBT27930IL_BlockRxMessage` to stop blocking the message.
- **filterValue**: Use same value as in `GBT27930IL_BlockRxMessage` to stop blocking the message.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: Blocking has been stopped successfully
- **-1**: There is no matching entry made by `GBT27930IL_BlockRxMessage`
- **-102**: An invalid parameter is used

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)