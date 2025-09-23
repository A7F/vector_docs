# J1939ILResetAllBlockedTxMessages

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILResetAllBlockedTxMessages();` // form 1
- `long J1939ILResetAllBlockedTxMessages(dbNode node);` // form 2

## Description

Resets the changes of all [J1939ILBlockTxMessage](CAPLfunctionJ1939ILBlockTxMessage.md) calls.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: Blocking of all messages has been stopped successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

## Example

—
