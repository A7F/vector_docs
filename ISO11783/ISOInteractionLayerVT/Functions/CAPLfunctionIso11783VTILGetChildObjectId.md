[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILGetChildObjectId.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_GetChildObjectId**

# VTIL_GetChildObjectId

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_GetChildObjectId(dbNode workingSetMaster, dword objectId, dword index, long & childObjectId); // form 1`
- `long VTIL_GetChildObjectId(dword addressWorkingSetMaster, dword objectId, dword index, long & childObjectId); // form 2`
- `long VTIL_GetChildObjectId(dbNode vt, dbNode workingSetMaster, dword objectId, dword index, long & childObjectId); // form 3`
- `long VTIL_GetChildObjectId(dbNode vt, dword addressWorkingSetMaster, dword objectId, dword index, long & childObjectId); // form 4`

## Description

Returns the ID of an object which is contained by a parent object. You can obtain the number of child objects with method [VTIL_GetNumberOfChildObjects](CAPLfunctionIso11783VTILGetNumberOfChildObjects.md).

## Parameters

- **vt**: VT simulation node to apply the function.
- **workingSetMaster**: Working Set Master which provides the Object Pool.
- **addressWorkingSetMaster**: Address of the Working Set Master which provides the Object Pool.
- **objectId**: Object ID of the parent object.
- **index**: Index of the child object in the object list of the parent object. The first index is 0.
- **childObjectId**: Returns the ID of the object at the specified index. If there is no child object for the specified index the value of childObjectId is set to -1.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 3, 4

```plaintext
dword index, numberOfChildObjects;
long childObjectId;

// iterate over all children of the object with objectId = 1000
if (VTIL_GetNumberOfChildObjects(VT, Loader, 1000, numberOfChildObjects) == 0)
{
  for (index = 0; index < numberOfChildObjects; ++index)
  {
    if (VTIL_GetChildObjectId(VT, Loader, 1000, index, childObjectId) == 0)
    {
      Write("ID of child object at index %u is %i", index, childObjectId);
    }
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)