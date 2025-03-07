[J1939ILBlockRxMessage](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILBlockRxMessage.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILBlockRxMessage

# J1939ILBlockRxMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILBlockRxMessage(dword pgn, dword sourceAddress, qword filterMask, qword filterValue); // form 1
long J1939ILBlockRxMessage(dbNode node, dword pgn, dword sourceAddress, qword filterMask, qword filterValue); // form 2
```

## Description

Prevents processing of a received message by the interaction layer. The message to block is specified by PGN, destination source address and a part of the first eight data bytes. To revert this command you can use [J1939ILResetBlockedRxMessage](CAPLfunctionJ1939ILResetBlockedRxMessage.md) or [J1939ILResetAllBlockedRxMessages](CAPLfunctionJ1939ILResetAllBlockedRxMessages.md).

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

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)