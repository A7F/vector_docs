[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILResetAllManipulatedMessages.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_ResetAllManipulatedMessages**

# TCIL_ResetAllManipulatedMessages

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_ResetAllManipulatedMessages(); // form 1
long TCIL_ResetAllManipulatedMessages(dbNode node); // form 2
```

## Description

Resets the changes of all [TCIL_ManipulateMessage](CAPLfunctionIso11783TCILManipulateMessage.md) calls.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: Manipulation of all messages has been stopped successfully
- **< 0**: An error has occurred, see error codes

## Example

—
