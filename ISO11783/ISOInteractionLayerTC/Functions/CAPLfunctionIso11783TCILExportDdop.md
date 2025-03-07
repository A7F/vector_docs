[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILExportDdop.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_ExportDdop**

# TCIL_ExportDdop

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_ExportDdop(dbNode client, char ddopPath[]); // form 1`
- `long TCIL_ExportDdop(dword addressClient, char ddopPath[]); // form 2`
- `long TCIL_ExportDdop(dbNode tc, dbNode client, char ddopPath[]); // form 3`
- `long TCIL_ExportDdop(dbNode tc, dword addressClient, char ddopPath[]); // form 4`

## Description

Exports the device descriptor object pool of the Task Controller client into a file.

## Parameters

- **client**: Task Controller client which provides the device descriptor object pool with corresponding sections.
- **addressClient**: Address of the Task Controller client which provides the device descriptor object pool with corresponding sections.
- **tc**: Task Controller simulation node to apply the function.
- **ddopPath**: Path of the target DDOP file (*.xml).

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 3

```c
long result;
result = TCIL_ExportDdop(TC, Sprayer, "xml\\sprayerV1.xml");
if (result < 0)
{
  TestStepFail("Failed to export DDOP!");
}
```

[TCIL_ExportAllDdops](CAPLfunctionIso11783TCILExportAllDdops.md)

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)