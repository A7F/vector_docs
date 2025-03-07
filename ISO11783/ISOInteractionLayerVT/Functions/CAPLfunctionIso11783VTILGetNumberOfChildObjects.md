[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILGetNumberOfChildObjects.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_GetNumberOfChildObjects**

# VTIL_GetNumberOfChildObjects

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_GetNumberOfChildObjects(dbNode workingSetMaster, dword objectId, dword & numberOfChildObjects); // form 1`
- `long VTIL_GetNumberOfChildObjects(dword addressWorkingSetMaster, dword objectId, dword & numberOfChildObjects); // form 2`
- `long VTIL_GetNumberOfChildObjects(dbNode vt, dbNode workingSetMaster, dword objectId, dword & numberOfChildObjects); // form 3`
- `long VTIL_GetNumberOfChildObjects(dbNode vt, dword addressWorkingSetMaster, dword objectId, dword & numberOfChildObjects); // form 4`

## Description

Returns the number of child objects which are contained in an object.

## Parameters

- **vt**: VT simulation node to apply the function.
- **workingSetMaster**: Working Set Master which provides the Object Pool.
- **addressWorkingSetMaster**: Address of the Working Set Master which provides the Object Pool.
- **objectId**: Object ID of the parent object.
- **numberOfChildObjects**: Returns the number of child objects contained in the parent object.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

See [VTIL_GetChildObjectId](CAPLfunctionIso11783VTILGetChildObjectId.md)

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)