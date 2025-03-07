[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILResetBlockedTxMessage.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_ResetBlockedTxMessage**

# VTIL_ResetBlockedTxMessage

[Valid for: CANoe DE • CANoe4SW DE](../../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long VTIL_ResetBlockedTxMessage(dword pgn, dword destinationAddress, qword filterMask, qword filterValue); // form 1
long VTIL_ResetBlockedTxMessage(dbNode node, dword pgn, dword destinationAddress, qword filterMask, qword filterValue); // form 2
```

## Description

Resets the change of a single [ISO11783VTIL_BlockTxMessage](CAPLfunctionIso11783VTILBlockTxMessage.md) call. The message to unblock is specified by PGN, destination address and a part of the first eight data bytes.

## Parameters

- **pgn**: Use same value as in `ISO11783IL_BlockTxMessage` to stop blocking the message.
- **destinationAddress**: Use same value as in `ISO11783IL_BlockTxMessage` to stop blocking the message.
- **filterMask**: Use same value as in `ISO11783IL_BlockTxMessage` to stop blocking the message.
- **filterValue**: Use same value as in `ISO11783IL_BlockTxMessage` to stop blocking the message.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: Blocking has been stopped successfully
- **-1**: There is no matching entry made by `ISO11783IL_BlockTxMessage`
- **-102**: An invalid parameter is used

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)