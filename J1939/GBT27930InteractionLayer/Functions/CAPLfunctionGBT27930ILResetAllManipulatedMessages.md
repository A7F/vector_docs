[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILResetAllManipulatedMessages.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GB/T 27930 IL](../CAPLfunctionsGBT27930ILOverview.md) » GBT27930IL_ResetAllManipulatedMessages

# GBT27930IL_ResetAllManipulatedMessages

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_ResetAllManipulatedMessages(); // form 1
long GBT27930IL_ResetAllManipulatedMessages(dbNode node); // form 2
```

## Description

Resets the changes of all [GBT27930IL_ManipulateMessage](CAPLfunctionGBT27930ILManipulateMessage.md) calls.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: Manipulation of all messages has been stopped successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
