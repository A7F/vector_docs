[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILRegisterObjectPool.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_RegisterObjectPool

# VTIL_RegisterObjectPool

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_RegisterObjectPool(dbNode workingSetMaster, char[] objectPoolPath[], char[] versionLabel); // form 1`
- `long VTIL_RegisterObjectPool(dword addressWorkingSetMaster, char[] objectPoolPath[], char[] versionLabel); // form 2`
- `long VTIL_RegisterObjectPool(dbNode vt, dbNode workingSetMaster, char[] objectPoolPath[], char[] versionLabel); // form 3`
- `long VTIL_RegisterObjectPool(dbNode vt, dword addressWorkingSetMaster, char[] objectPoolPath[], char[] versionLabel); // form 4`

## Description

Registers an object pool file (iop). A registered object pool can be loaded via the Load Version command. For more information see chapter [Save Object Pools in VT Storage](../../../../Shared/ISO11783/ISO11783ILVT.md).

## Parameters

- **vt**: VT simulation node to apply the function
- **workingSetMaster**: Working Set Master to which the Object Pool belongs
- **addressWorkingSetMaster**: Address of the Working Set Master to which the Object Pool belongs
- **objectPoolPath**: Path of an object pool file (*.iop). Path has to be absolute or relative relating to the folder of the CANoe configuration.
- **versionLabel**: The Virtual Terminal IL stores the object pool with this label

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 3, 4

```plaintext
long result;
result = VTIL_RegisterObjectPool( VT, Sprayer, "iop\\sprayerV1.iop", "sprayV1");
if (result < 0)
{
  TestStepFail("Failed to register file!");
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)