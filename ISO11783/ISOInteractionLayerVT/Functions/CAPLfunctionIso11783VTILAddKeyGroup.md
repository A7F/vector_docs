[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILAddKeyGroup.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_AddKeyGroup

# VTIL_AddKeyGroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `VTIL_AddKeyGroup(dword maskIndex, dword position, dbNode workingSetMaster, dword keyGroupId); // form 1`
- `VTIL_AddKeyGroup(dword maskIndex, dword position, dword workingSetMasterAddress, dword keyGroupId); // form 2`
- `VTIL_AddKeyGroup(dbNode vt, dword maskIndex, dword position, dbNode workingSetMaster, dword keyGroupId); // form 3`
- `VTIL_AddKeyGroup(dbNode vt, dword maskIndex, dword position, dword workingSetMasterAddress, dword keyGroupId); // form 4`

## Description

Adds a Key Group to a User-Layout Data Mask of the Virtual Terminal.

VT IL does not store added Key Groups in the CANoe DE product configuration. But the VT Window stores the layout of User-Layout Masks. If the VT IL is [coupled with a VT Window](../../../../CANoeCANalyzer/ISO11783/VirtualTerminalWindow/VTWindow.md#InteractionVTIL), then VT Window transfers the layout of User-Layout Masks to the VT IL at startup.

You can remove a Key Group with [VTIL_RemoveKeyGroup](CAPLfunctionIso11783VTILRemoveKeyGroup.md) or [VTIL_ClearUserLayoutMask](CAPLfunctionIso11783VTILClearUserLayoutMask.md).

## Parameters

- **maskIndex**: Index of the User-Layout Mask, 0..10. Value of maskIndex must be smaller than the number of User-Layout Masks (which can be configured with [VTIL_SetNodeProperty](CAPLfunctionIso11783VTILSetNodeProperty.md)).
- **position**: Adds the Key Group at this position in the User-Layout Soft Key Mask, 0..64. Position must be smaller than the number of User-Layout Soft Keys (which can be configured with [VTIL_SetNodeProperty](CAPLfunctionIso11783VTILSetNodeProperty.md)).
- **workingSetMaster**: Working Set Master which provides the Key Group.
- **workingSetMasterAddress**: Address of the Working Set Master which provides the Key Group.
- **keyGroupId**: Object ID of the Key Group.
- **vt**: VT simulation node to apply the function.

## Return Values

- **0**: Key Group is successfully added.
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

## Example

```plaintext
long result;
// configure one User-Layout Mask with 10 User-Layout Soft Keys
VTIL_SetNodeProperty("numberOfUserLayoutDataMasks", 1);
VTIL_SetNodeProperty("numberOfUserLayoutSoftKeys", 10);
// add Key Group 3000 of implement with address 21 at position 0
result = VTIL_AddKeyGroup(0, 0, 21, 3000);
if (result != 0)
{
  write("Failed to add Key Group 3000 (error %i)", result);
}
// add Key Group 3001 of implement with address 22 at position 3
result = VTIL_AddKeyGroup(0, 3, 22, 3001);
if (result != 0)
{
  write("Failed to add Key Group 3001 (error %i)", result);
}

// remove Key Group at position 0
result = VTIL_RemoveKeyGroup(0, 0);
if (result != 0)
{
  write("Failed to remove Key Group at position 0 (error %i)", result);
}
// remove Key Group at position 3
result = VTIL_RemoveKeyGroup(0, 3);
if (result != 0)
{
  write("Failed to remove Key Group at position 3 (error %i)", result);
}
```

[Further Functions for **VT – Handling (User-Layout Mask)**](../CAPLfunctionsISOILVTOverview.md#VTHandlingUserLayoutMask)
