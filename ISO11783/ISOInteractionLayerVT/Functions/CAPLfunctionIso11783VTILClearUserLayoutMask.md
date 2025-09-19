[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILClearUserLayoutMask.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_ClearUserLayoutMask

# VTIL_ClearUserLayoutMask

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `VTIL_ClearUserLayoutMask (dword maskIndex, dword options); // form 1`
- `VTIL_ClearUserLayoutMask (dbNode vt, dword maskIndex, dword options); // form 2`

## Description

Removes all Window Masks and all Key Groups from a User-Layout Mask of the Virtual Terminal.

## Parameters

- **maskIndex**: Index of the User-Layout Mask, 0..10. Value of maskIndex must be smaller than the number of User-Layout Masks (which can be configured with [VTIL_SetNodeProperty](CAPLfunctionIso11783VTILSetNodeProperty.md)).

- **options**:
  - 0: No additional option
  - 1: Send a VT On User-Layout Hide/Show message for every removed Window Mask or Key Group

- **vt**: VT simulation node to apply the function.

## Return Values

- **0**: Window Masks and Key Groups are successfully removed.
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

## Example

```plaintext
long result;
// configure one User-Layout Data Mask with 10 User-Layout Soft Keys
VTIL_SetNodeProperty("numberOfUserLayoutDataMasks", 1);
VTIL_SetNodeProperty("numberOfUserLayoutSoftKeys", 10);
// add Window Mask 3000 of implement with address 21 at position (0|0)
result = VTIL_AddWindowMask(0, 0, 0, 21, 3000);
if (result != 0)
{
  write("Failed to add Window Mask 3000 (error %i)", result);
}
// add Key Group 3100 of implement with address 21 at position 0
result = VTIL_AddKeyGroup(0, 0, 21, 3100);
if (result != 0)
{
  write("Failed to add Key Group 3100 (error %i)", result);
}

// remove all Window Masks and Key Groups
result = VTIL_ClearUserLayoutMask(0, 1);
if (result != 0)
{
  write("Failed to clear User-Layout mask (error %i)", result);
}
```

[Further Functions for **VT – Handling (User-Layout Mask)**](../CAPLfunctionsISOILVTOverview.md#VTHandlingUserLayoutMask)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
