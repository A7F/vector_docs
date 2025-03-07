[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILGetDeviceParameters.md)

## TCIL_GetDeviceParameters

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_GetDeviceParameters

### Tool Availability

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Function Syntax

- `long TCIL_GetDeviceParameters(byte addressClient, char designator[], char version[], byte deviceName[], char serialNumber[], byte structureLabel[], dword& lengthOfStructureLabel, byte localizationLabel[]); // form 1`
- `long TCIL_GetDeviceParameters(dbNode tc, byte addressClient, char designator[], char version[], byte deviceName[], char serialNumber[], byte structureLabel[], dword& lengthOfStructureLabel, byte localizationLabel); // form 2`

### Description

Returns parameters of the client device which are contained in the Device XML element (DVC) of the device description.

### Parameters

- **tc**: TC simulation node to apply the function.
- **addressClient**: Address of the TC client node the data entity belongs to.
- **designator**: Returns the device designator of the client device (as a NULL-terminated string).
- **version**: Returns the software version of the client device (as a NULL-terminated string).
- **deviceName**: Returns the NAME of the client device (as a byte array).
- **serialNumber**: Returns the serial number of the client device (as a NULL-terminated string).
- **structureLabel**: Returns the label of device descriptor structure (as a byte array).
- **lengthOfStructureLabel**: Returns the length of the structureLabel.
- **localizationLabel**: Returns the label of the device descriptor localization (as a byte array).

### Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

### Example

Example (Form 2, applicable in a test node)

```c
long result;
char designator[33];
char version[33];
byte deviceName[8];
char serialNumber[33];
byte structureLabel[33];
dword lengthOfStructureLabel;
byte localizationLabel[7];

result = TCIL_GetDeviceParameters(TC, clientAddress, designator, version, deviceName, serialNumber, structureLabel, lengthOfStructureLabel, localizationLabel);
if (result < 0)
{
  write("TCIL_GetDeviceParameters failed with error %i", result);
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)