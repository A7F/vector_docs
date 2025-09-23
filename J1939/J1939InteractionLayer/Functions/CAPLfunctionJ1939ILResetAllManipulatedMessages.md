# J1939ILResetAllManipulatedMessages

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILResetAllManipulatedMessages(); // form 1
long J1939ILResetAllManipulatedMessages(dbNode node); // form 2
```

## Description

Resets the changes of all [J1939ILManipulateMessage](CAPLfunctionJ1939ILManipulateMessage.md) calls.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: Manipulation of all messages has been stopped successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
