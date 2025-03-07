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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)