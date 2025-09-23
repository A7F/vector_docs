[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILAddWindowMask.md)

## CAPL Functions » ISO11783 » Virtual Terminal Interaction Layer (VT IL) » VTIL_AddWindowMask

### Valid for: CANoe DE • CANoe4SW DE

### Function Syntax

- `VTIL_AddWindowMask(dword maskIndex, dword column, dword row, dbNode workingSetMaster, dword windowMaskId); // form 1`
- `VTIL_AddWindowMask(dword maskIndex, dword column, dword row, dword workingSetMasterAddress, dword windowMaskId); // form 2`
- `VTIL_AddWindowMask(dbNode vt, dword maskIndex, dword column, dword row, dbNode workingSetMaster, dword windowMaskId); // form 3`
- `VTIL_AddWindowMask(dbNode vt, dword maskIndex, dword column, dword row, dword workingSetMasterAddress, dword windowMaskId); // form 4`

### Description

Adds a Window Mask to a User-Layout Data Mask of the Virtual Terminal.

VT IL does not store added Window Masks in the CANoe DE product configuration. But the VT Window stores the layout of User-Layout Masks. If the VT IL is [coupled with a VT Window](../../../../CANoeCANalyzer/ISO11783/VirtualTerminalWindow/VTWindow.md#InteractionVTIL), then VT Window transfers the layout of User-Layout Masks to the VT IL at startup.

You can remove a Window Mask with [VTIL_RemoveWindowMask](CAPLfunctionIso11783VTILRemoveWindowMask.md) or [VTIL_ClearUserLayoutMask](CAPLfunctionIso11783VTILClearUserLayoutMask.md).

### Parameters

- **maskIndex**: Index of the User-Layout Mask, 0..10. Value of maskIndex must be smaller than the number of User-Layout Masks (which can be configured with [VTIL_SetNodeProperty](CAPLfunctionIso11783VTILSetNodeProperty.md)).
- **column**: Adds the Window Mask at this column in the User-Layout Data Mask, 0..1.
- **row**: Adds the Window Mask at this row in the User-Layout Data Mask, 0..5.
- **workingSetMaster**: Working Set Master which provides the Window Mask.
- **workingSetMasterAddress**: Address of the Working Set Master which provides the Window Mask.
- **windowMaskId**: Object ID of the Window Mask.
- **vt**: VT simulation node to apply the function.

### Return Values

- **0**: Window Mask is successfully added.
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

### Example

```plaintext
long result;
// configure one User-Layout Data Mask
VTIL_SetNodeProperty("numberOfUserLayoutDataMasks", 1);
// add Window Mask 3000 of implement with address 21 at position (0|0)
result = VTIL_AddWindowMask(0, 0, 0, 21, 3000);
if (result != 0)
{
  write("Failed to add Window Mask 3000 (error %i)", result);
}
// add Window Mask 4000 of implement with address 22 at position (0|1)
result = VTIL_AddWindowMask(0, 0, 1, 22, 4000);
if (result != 0)
{
  write("Failed to add Window Mask 4000 (error %i)", result);
}

// remove Window Mask at position (0|0)
result = VTIL_RemoveWindowMask(0, 0, 0);
if (result != 0)
{
  write("Failed to remove Window Mask at position (0|0)(error %i)", result);
}
// remove Window Mask at position (0|1)
result = VTIL_RemoveWindowMask(0, 0, 1);
if (result != 0)
{
  write("Failed to remove Window Mask at position (0|1) (error %i)", result);
}
```

[Further Functions for **VT – Handling (User-Layout Mask)**](../CAPLfunctionsISOILVTOverview.md#VTHandlingUserLayoutMask)
