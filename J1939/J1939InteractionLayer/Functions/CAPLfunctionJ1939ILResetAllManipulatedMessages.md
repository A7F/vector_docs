[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILResetAllManipulatedMessages.md)

**CAPL Functions** » **J1939** » **J1939 IL** » J1939ILResetAllManipulatedMessages

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

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
