[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILGetIdOfVisibleObject.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_GetIdOfVisibleObject

# VTIL_GetIdOfVisibleObject

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_GetIdOfVisibleObject(dbNode workingSetMaster, dword x, dword y, dword objectType, dword& foundObjectId); // form 1`
- `long VTIL_GetIdOfVisibleObject(dword addressWorkingSetMaster, dword x, dword y, dword objectType, dword& foundObjectId); // form 2`
- `long VTIL_GetIdOfVisibleObject(dbNode vt, dbNode workingSetMaster, dword x, dword y, dword objectType, dword& foundObjectId); // form 3`
- `long VTIL_GetIdOfVisibleObject(dbNode vt, dword addressWorkingSetMaster, dword x, dword y, dword objectType, dword& foundObjectId); // form 4`

## Description

Returns the object ID of the visible object that is displayed at the specified position in the current Data or Alarm Mask. You can define the type of object you are looking for with the parameter **objectType**.

## Parameters

- **vt**: VT simulation node to apply the function.
- **workingSetMaster**: Working Set Master which provides the Object Pool.
- **addressWorkingSetMaster**: Address of the Working Set Master which provides the Object Pool or -1 (0xFFFFFFFF) if the Object Pool of the currently active Working Set is used, 0..253 or -1.
- **x**: X position in pixels relative to top left corner of Data Mask area, 0..65535.
- **y**: Y position in pixels relative to top left corner of Data Mask area, 0..65535.
- **objectType**: Target object type of the visible object or -1 (0xFFFFFFFF) if topmost visible object is used, 0..255 or -1.
- **foundObjectId**: Returns the object ID of the visible object.

## Return Values

- **0**: The object ID was successfully determined.
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).
- **–2127**: There is no visible object with the specified object type at the specified position.

## Example

```c
dword GetIdOfDisplayedButton(dword x, dword y)
{
  long result;
  dword objectID;
  const byte objectTypeButton = 6;
  result = VTIL_GetIdOfVisibleObject(-1, x, y, 6, objectID);
  if (result != 0)
  {
    write("GetIdOfVisibleObject failed with error %i", result);
    return 0xFFFF;
  }
  return objectID;
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)