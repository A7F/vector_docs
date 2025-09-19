[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILPDDObjectPoolDeactivate.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_PDDObjectPoolDeactivate

# Iso11783IL_PDDObjectPoolDeactivate

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_PDDObjectPoolDeactivate();` // form 1
- `long Iso11783IL_PDDObjectPoolDeactivate(dbNode implement);` // form 2

## Description

The function sends an **Object-pool Deactivate** message to the Task Controller and disconnects the connection to the Task Controller.

## Parameters

- **implement**: Simulation node to apply the function.

## Return Values

[error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
if (Iso11783IL_PDDObjectPoolDeactivate() == 0) {
  write("Node has disconnected from the Task Controller");
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
