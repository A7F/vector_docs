[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILBlockRxMessage.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_BlockRxMessage**

# GBT27930IL_BlockRxMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_BlockRxMessage(dword pgn, dword sourceAddress, qword filterMask, qword filterValue); // form 1
long GBT27930IL_BlockRxMessage(dbNode node, dword pgn, dword sourceAddress, qword filterMask, qword filterValue); // form 2
```

## Description

Prevents processing of a received message by the interaction layer.

The message to block is specified by PGN, destination source address and a part of the first eight data bytes.

To revert this command you can use [GBT27930IL_ResetBlockedRxMessage](CAPLfunctionGBT27930ILResetBlockedRxMessage.md) or [GBT27930IL_ResetAllBlockedTxMessages](CAPLfunctionGBT27930ILResetAllBlockedTxMessages.md).

## Parameters

- **pgn**: The message with this PGN shall be blocked.
- **sourceAddress**:
  - 0 - 255: The message which is sent to this address shall be blocked.
  - 0xFFFFFFFF (-1): The source address of the message doesn’t matter.
- **filterMask**: Defines the bits of the message which shall be used to identify the message.
- **filterValue**: Defines the value of the bits of the message which shall be used to identify the message. If the value of the masked bits of a received message is equal to this value then the data of the message is blocked.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: Manipulation is set successfully
- **-102**: An invalid parameter is used

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)