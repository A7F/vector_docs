[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILPDDSetValueRaw.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_PDDSetValueRaw, Iso11783IL_PDDSetValuePhysical

# Iso11783IL_PDDSetValueRaw, Iso11783IL_PDDSetValuePhysical

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_PDDSetValueRaw(dword ddi, dword elementNumber, long value); // form 1`
- `long Iso11783IL_PDDSetValueRaw(dbNode implement, dword ddi, dword elementNumber, long value); // form 2`
- `long Iso11783IL_PDDSetValuePhysical(dword ddi, dword elementNumber, double value); //form 3`
- `long Iso11783IL_PDDSetValuePhysical(dbNode implement, dword ddi, dword elementNumber, double value); // form 4`

## Description

Sets the value of a data entity (process variable) without sending any command.

## Parameters

- **ddi**: Data Dictionary Identifier, 0x0000.0xFFFF
- **elementNumber**: Element number, 0x000.0xFFF
- **value**: New value of the data entity (process variable)
- **implement**: Task Controller simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

**Example form 2**

```plaintext
SetActualAppRateUsingRawValue()
{
  // section 1: elementNumber = 3
  Iso11783IL_PDDSetValueRaw(Sprayer, 37, 3, 13360);
  // section 2: elementNumber = 4
  Iso11783IL_PDDSetValueRaw(Sprayer, 37, 4, 13950);
}
```

**Example form 4**

```plaintext
SetActualAppRateUsingRawValue()
{
  // section 1: elementNumber = 3
  Iso11783IL_PDDSetValuePhysical(Sprayer, 37, 3, 13.360);
  // section 2: elementNumber = 4
  Iso11783IL_PDDSetValuePhysical(Sprayer, 37, 4, 13.950);
}
```

[Iso11783IL_PDDGetValueRaw, Iso11783IL_PDDGetValuePhysical](CAPLfunctionIso11783ILPDDGetValueRaw.md)

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
