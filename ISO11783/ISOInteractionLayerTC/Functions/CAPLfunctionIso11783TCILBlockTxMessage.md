[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILBlockTxMessage.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_BlockTxMessage**

# TCIL_BlockTxMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_BlockTxMessage(dword pgn, dword destinationAddress, qword filterMask, qword filterValue); // form 1`
- `long TCIL_BlockTxMessage(dbNode node, dword pgn, dword destinationAddress, qword filterMask, qword filterValue); // form 2`

## Description

Prevents transmitting of a message generated and sent by the interaction layer. The message to block is specified by PGN, destination address, and a part of the first eight data bytes. To revert this command you can use [TCIL_ResetBlockedTxMessage](CAPLfunctionIso11783TCILResetBlockedTxMessage.md) or [TCIL_ResetAllBlockedTxMessages](CAPLfunctionIso11783TCILResetAllBlockedTxMessages.md).

## Parameters

- **pgn**: The message with this PGN shall be blocked.
- **destinationAddress**:
  - 0 - 255: The message which is sent to this address shall be blocked.
  - 0xFFFFFFFF (-1): The destination address of the message doesn’t matter.
- **filterMask**: Defines the bits of the message which shall be used to identify the message.
- **filterValue**: Defines the value of the bits of the message which shall be used to identify the message. If the value of the masked bits of a sent message is equal to this value then the data of the message is blocked.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: Manipulation is set successfully
- **-102**: An invalid parameter is used

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
