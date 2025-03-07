[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILExportAllDdops.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_ExportAllDdops**

# TCIL_ExportAllDdops

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_ExportAllDdops(char ddopPath[]); // form 1
long TCIL_ExportAllDdops(dbNode tc, char ddopPath[]); // form 2
```

## Description

Exports the device descriptor object pools of all Task Controller clients into a file.

## Parameters

- **ddopPath**: Path of the target file (*.xml).
- **tc**: Task Controller simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 2

```plaintext
long result;
result = TCIL_ExportAllDdop(TC, "XML\\AllClientDDOPs.xml");
if (result < 0)
{
  TestStepFail("Failed to export DDOPs!");
}
```

[TCIL_ExportDdop](CAPLfunctionIso11783TCILExportDdop.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)