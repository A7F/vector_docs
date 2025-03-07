[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILRemoveWindowMask.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_RemoveWindowMask

# VTIL_RemoveWindowMask

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `VTIL_RemoveWindowMask(dword maskIndex, dword column, dword row); // form 1`
- `VTIL_RemoveWindowMask(dbNode vt, dword maskIndex, dword column, dword row); // form 2`

## Description

Removes a Window Mask from a User-Layout Data Mask of the Virtual Terminal.

## Parameters

- **maskIndex**: Index of the User-Layout Mask. Value of maskIndex must be smaller than the number of User-Layout Masks (which can be configured with [VTIL_SetNodeProperty](CAPLfunctionIso11783VTILSetNodeProperty.md)).
- **column**: Removes the Window Mask at this column in the User-Layout Data Mask, 0..1.
- **row**: Removes the Window Mask at this row in the User-Layout Data Mask, 0..5.
- **vt**: VT simulation node to apply the function.

## Return Values

- **0**: Window Mask is successfully removed.
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

## Example

See [VTIL_AddWindowMask](CAPLfunctionIso11783VTILAddWindowMask.md).

[Further Functions for **VT – Handling (User-Layout Mask)**](../CAPLfunctionsISOILVTOverview.md#VTHandlingUserLayoutMask)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)