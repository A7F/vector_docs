[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILResetAllBlockedTxMessages.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_ResetAllBlockedTxMessages

# VTIL_ResetAllBlockedTxMessages

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_ResetAllBlockedTxMessages();` // form 1
- `long VTIL_ResetAllBlockedTxMessages(dbNode node);` // form 2

## Description

Resets the changes of all [Iso11783VTIL_BlockTxMessage](CAPLfunctionIso11783VTILBlockTxMessage.md) calls.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: Blocking of all messages has been stopped successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
