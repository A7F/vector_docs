[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILPDDGetValueRaw.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_PDDGetValueRaw, Iso11783IL_PDDGetValuePhysical

# Iso11783IL_PDDGetValueRaw, Iso11783IL_PDDGetValuePhysical

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_PDDGetValueRaw(dword ddi, dword elementNumber, long& value); // form 1`
- `long Iso11783IL_PDDGetValueRaw(dbNode implement, dword ddi, dword elementNumber, long& value); // form 2`
- `long Iso11783IL_PDDGetValuePhysical(dword ddi, dword elementNumber, double& value); //form 3`
- `long Iso11783IL_PDDGetValuePhysical(dbNode implement, dword ddi, dword elementNumber, double& value); // form 4`

## Description

Gets the value of a data entity (process variable) without sending any command.

## Parameters

- **ddi**: Data Dictionary Identifier, 0x0000.0xFFFF.
- **elementNumber**: Element number, 0x000.0xFFF.
- **value**: Returns the value of the data entity (process variable).
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 2

```plaintext
double currentValue;
long result;
result = Iso11783IL_PDDGetValuePhysical(120, 2, currentValue);
```

[Iso11783IL_PDDSetValueRaw, Iso11783IL_PDDSetValuePhysical](CAPLfunctionIso11783ILPDDSetValueRaw.md)

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)