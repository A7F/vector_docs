[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILResetAllManipulatedMessages.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_ResetAllManipulatedMessages

# Iso11783IL_ResetAllManipulatedMessages

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long ISO11783IL_ResetAllManipulatedMessages(); // form 1`
- `long ISO11783IL_ResetAllManipulatedMessages(dbNode node); // form 2`

## Description

Resets the changes of all [ISO11783IL_ManipulateMessage](CAPLfunctionIso11783ILManipulateMessage.md) calls.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: Manipulation of all messages has been stopped successfully
- **< 0**: An error has occurred, see error codes

## Example

—
