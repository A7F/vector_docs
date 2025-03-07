[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783PDDUpdateDeviceDescription.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783PDDUpdateDeviceDescription

# Iso11783PDDUpdateDeviceDescription

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
The ISO11783 node layer allows the [segmented transmission of device descriptions](../../../../CANoeCANalyzer/ISO11783/processData/ProcessDataSegmentedTransmission.md).

## Function Syntax

```plaintext
long Iso11783PDDUpdateDeviceDescription( dword ecuHandle, char deviceCfgPath [] );
```

## Description

The function updates the current device description object pool at runtime. Only the device object and objects of type **DeviceValuePresentation** of the specified file are transmitted.

## Parameters

- **ecuHandle**  
  Handle of the ECU. The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md) beforehand or ZERO for general parameters.

- **deviceCfgPath**  
  Filename of the device configuration file. The file must be located in the directory of the CANoe configuration.

## Return Values

[error code](../CAPLfunctionsISONLErrorCodesPDDOnError.md)

## Example

```plaintext
if (Iso11783PDDUpdateDeviceDescription( ecuHandle, "Sprayer01.XML" ) == 0) {
  // after  the device value presentation has changed to English
  // the designators are changed too
  Iso11783PDDChangeDesignator ( ecuHandle, 1, "Tank volume" );
  Iso11783PDDChangeDesignator ( ecuHandle, 2, "App rate per area" );
} else {
  write( "Error while update file" );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)