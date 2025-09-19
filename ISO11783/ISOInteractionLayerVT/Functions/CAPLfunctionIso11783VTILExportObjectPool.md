[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILExportObjectPool.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_ExportObjectPool**

# VTIL_ExportObjectPool

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_ExportObjectPool(dbNode workingSetMaster, char objectPoolFilePath[]); // form 1`
- `long VTIL_ExportObjectPool(dword addressWorkingSetMaster, char objectPoolFilePath[]); // form 2`
- `long VTIL_ ExportObjectPool (dbNode vt, dbNode workingSetMaster, char objectPoolFilePath []); // form 3`
- `long VTIL_ ExportObjectPool (dbNode vt, dword addressWorkingSetMaster, char objectPoolFilePath []); // form 4`

## Description

Exports the current object pool of the Working Set Master into a file (*.iop). An existing file is overwritten.

## Parameters

- **vt**: VT simulation node to apply the function
- **workingSetMaster**: Working Set Master which object pool is exported (must not be the active Working Set).
- **addressWorkingSetMaster**: Address of the Working Set Master which object pool is exported (must not be the active Working Set).
- **objectPoolPath**: Path to the *.iop file the object pool has to be exported to. Path has to be absolute or relative relating to the folder of the CANoe configuration.
- **versionLabel**: The Virtual Terminal IL stores the object pool with this label

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 3

```c
long result;
result = VTIL_ExportObjectPool(VT, Loader, "c:\\temp\\Loader.iop");
switch (result)
{
  case 0: TestStepPass(); break;
  case -2113: TestStepFail("Invalid parameter!"); break;
  case -2122: TestStepFail("Failed to export object pool to file!"); break;
  default: TestStepFail("Unexpected error!"); break;
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
