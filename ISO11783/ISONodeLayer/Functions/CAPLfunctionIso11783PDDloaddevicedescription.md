[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783PDDloaddevicedescription.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » **Iso11783PDDLoadDeviceDescription**

# Iso11783PDDLoadDeviceDescription

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
In case the corresponding node is running in the distributed environment, the machine configuration file has to be registered under **Configuration | Options… | Configuration Settings | User files** in **CANoe**.  
The ISO11783 node layer allows the [segmented transmission of device descriptions](../../../../CANoeCANalyzer/ISO11783/processData/ProcessDataSegmentedTransmission.md).

## Function Syntax

```plaintext
long Iso11783PDDLoadDeviceDescription( dword ecuHandle, char deviceCfgPath[] );
```

## Description

The function creates a process data dictionary from a machine configuration file (XML).

## Parameters

- **ecuHandle**  
  Handle of the ECU.  
  The handle must previously have been created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).

- **deviceCfgPath**  
  Filename of the machine configuration file.  
  The file must be located in the directory of the **CANoe** configuration.

## Return Values

[Error code](../CAPLfunctionsISONLErrorCodesPDDOnError.md)

## Example

```plaintext
if (Iso11783PDDLoadDeviceDescription( ecuHandle, "Sprayer.XML" ) == 0) {
  Iso11783PDDConnectEnvVar ( ecuHandle, 0x0060, 1, "EvSprayer_TankVolume" );
  Iso11783PDDConnectEnvVar ( ecuHandle, 0x0048, 2, "EvSprayer_AppRatePerArea" );
}
else {
  write( "Error while load task file" );
}
```

© Vector Informatik GmbH  
**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
