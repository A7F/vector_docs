[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILResetDelayedRxMessage.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GB/T 27930 IL](../CAPLfunctionsGBT27930ILOverview.md) » GBT27930IL_ResetDelayedRxMessage

# GBT27930IL_ResetDelayedRxMessage

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_ResetDelayedRxMessage(dword pgn, dword sourceAddress, qword filterMask, qword filterValue, dword behavior); // form 1
long GBT27930IL_ResetDelayedRxMessage(dbNode node, dword pgn, dword sourceAddress, qword filterMask, qword filterValue, dword behavior); // form 2
```

## Description

Resets the change of a single [GBT27930IL_DelayRxMessage](CAPLfunctionGBT27930ILDelayRxMessage.md) call. The corresponding message is specified by PGN, source address, destination address and a part of the first eight data bytes.

## Parameters

- **pgn**: Use same value as in `GBT27930IL_DelayRxMessage` to stop manipulation of the message.
- **sourceAddress**: Use same value as in `GBT27930IL_DelayRxMessage` to stop manipulation of the message.
- **filterMask**: Use same value as in `GBT27930IL_DelayRxMessage` to stop manipulation of the message.
- **filterValue**: Use same value as in `GBT27930IL_DelayRxMessage` to stop manipulation of the message.
- **behavior**:
  - 0: Do not process currently delayed messages
  - 1: Process currently delayed messages after the defined delay
- **node**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **-102**: An invalid parameter is used

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
