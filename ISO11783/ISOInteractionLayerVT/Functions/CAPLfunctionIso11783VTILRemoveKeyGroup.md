[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILRemoveKeyGroup.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_RemoveKeyGroup

# VTIL_RemoveKeyGroup

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `VTIL_RemoveKeyGroup(dword maskIndex, dword position); // form 1`
- `VTIL_RemoveKeyGroup(dbNode vt, dword maskIndex, dword position); // form 2`

## Description

Removes a Key Group from a User-Layout Soft Key Mask of the Virtual Terminal.

## Parameters

- **maskIndex**: Index of the User-Layout Mask, 0..10. Value of maskIndex must be smaller than the number of User-Layout Masks (which can be configured with [VTIL_SetNodeProperty](CAPLfunctionIso11783VTILSetNodeProperty.md)).

- **position**: Removes the Key Group at this position in the User-Layout Soft Key Mask, 0..64. Position must be smaller than the number of User-Layout Soft Keys (which can be configured with [VTIL_SetNodeProperty](CAPLfunctionIso11783VTILSetNodeProperty.md)).

- **vt**: VT simulation node to apply the function.

## Return Values

- **0**: Key Group is successfully removed.
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

## Example

See [VTIL_AddKeyGroup](CAPLfunctionIso11783VTILAddKeyGroup.md)

[Further Functions for **VT – Handling (User-Layout Mask)**](../CAPLfunctionsISOILVTOverview.md#VTHandlingUserLayoutMask)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
