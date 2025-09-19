[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILIsObjectVisible.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_IsObjectVisible**

# VTIL_IsObjectVisible

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_IsObjectVisible(dbNode workingSetMaster, dword typeOfActiveMask, dword objectId, dword & isVisible); // form 1`
- `long VTIL_IsObjectVisible(dword addressWorkingSetMaster, dword typeOfActiveMask, dword objectId, dword & isVisible); // form 2`
- `long VTIL_IsObjectVisible(dbNode vt, dbNode workingSetMaster, dword typeOfActiveMask, dword objectId, dword & isVisible); // form 3`
- `long VTIL_IsObjectVisible(dbNode vt, dword addressWorkingSetMaster, dword typeOfActiveMask, dword objectId, dword & isVisible); // form 4`

## Description

Checks if an object is visible in the current **Data Mask** or **Soft Key Mask**.

## Parameters

- **vt**: VT simulation node to apply the function.
- **workingSetMaster**: Working Set Master which provides the Object Pool.
- **addressWorkingSetMaster**: Address of the Working Set Master which provides the Object Pool.
- **typeOfActiveMask**: Specifies if function checks the visibility of the object in the active Data Mask or in the active Soft Key Mask.
  - 0: Data mask
  - 1: Soft Key mask
- **objectId**: Object ID of visible Data Mask or Alarm Mask.
- **isVisible**: Returns the visibility of the object.
  - 0: Object is not visible
  - 1: Object is visible

## Return Values

- **0**: Function has been executed successfully.
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

## Example

—

© Vector Informatik GmbH
**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
