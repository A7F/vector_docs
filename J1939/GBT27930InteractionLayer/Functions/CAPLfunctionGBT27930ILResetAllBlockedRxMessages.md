[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILResetAllBlockedRxMessages.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GB/T 27930 IL](../CAPLfunctionsGBT27930ILOverview.md) » GBT27930IL_ResetAllBlockedRxMessages

# GBT27930IL_ResetAllBlockedRxMessages

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_ResetAllBlockedRxMessages(); // form 1`
- `long GBT27930IL_ResetAllBlockedRxMessages(dbNode node); // form 2`

## Description

Resets the changes of all [GBT27930IL_BlockRxMessage](CAPLfunctionGBT27930ILBlockRxMessage.md) calls.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: Blocking of all messages has been stopped successfully.
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

## Example

—

[See Also](javascript:void(0);)