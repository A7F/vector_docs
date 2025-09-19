[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILResetAllBlockedTxMessages.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_ResetAllBlockedTxMessages**

# GBT27930IL_ResetAllBlockedTxMessages

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_ResetAllBlockedTxMessages(); // form 1`
- `long GBT27930IL_ResetAllBlockedTxMessages(dbNode node); // form 2`

## Description

Resets the changes of all [GBT27930IL_BlockTxMessage](CAPLfunctionGBT27930ILBlockTxMessage.md) calls.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: Blocking of all messages has been stopped successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
