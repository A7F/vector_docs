[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILPDDObjectPoolDelete.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_PDDObjectPoolDelete

# Iso11783IL_PDDObjectPoolDelete

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_PDDObjectPoolDelete(); // form 1`
- `long Iso11783IL_PDDObjectPoolDelete(dbNode implement); // form 2`

## Description

The function deletes the current device description object pool and sends an **Object-pool Delete** message to the Task Controller.

Contrary to [Iso11783IL_PDDDelete](CAPLfunctionIso11783ILpdddelete.md) the connection to the Task Controller is not removed.

## Parameters

- **implement**: Simulation node to apply the function.

## Return Values

[error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```c
if (Iso11783IL_PDDObjectPoolDelete() == 0) {
  write("Object pool is deleted and Object-Pool delete message is sent successfully");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
