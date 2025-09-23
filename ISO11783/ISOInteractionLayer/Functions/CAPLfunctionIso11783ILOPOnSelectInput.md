[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPOnSelectInput.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPOnSelectInput

# Iso11783IL_OPOnSelectInput

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void Iso11783IL_OPOnSelectInput( dword objectID, dword what );
```

## Description

The function is called by the node layer, if an input object is selected.

## Parameters

- **objectID**: Object ID of the selected input object
- **what**:
  - 0: input object is not selected
  - 1: input object is selected
  - 2: input object is opened

## Return Values

—

## Example

```plaintext
void Iso11783IL_OPOnSelectInput( dword objectID, dword what )
{
}
```
