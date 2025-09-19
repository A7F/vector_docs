[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILPDDUpdateDeviceDescription.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_PDDUpdateDeviceDescription

# Iso11783IL_PDDUpdateDeviceDescription

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
The ISO11783 Interaction Layer allows the [segmented transmission of device descriptions](../../../../CANoeCANalyzer/ISO11783/processData/ProcessDataSegmentedTransmission.md).

## Function Syntax

```plaintext
long Iso11783IL_PDDUpdateDeviceDescription( char deviceCfgPath [] ); // form 1
long Iso11783IL_PDDUpdateDeviceDescription( dbNode implement, char deviceCfgPath [] ); // form 2
```

## Description

The function updates the current device description object pool at runtime.

Only the device object and objects of type **DeviceValuePresentation** of the specified file are transmitted.

## Parameters

- **deviceCfgPath**  
  Filename of the device configuration file. The file must be located in the directory of the CANoe configuration.

- **implement**  
  Simulation node to apply the function.

## Return Values

[error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
if (Iso11783IL_PDDUpdateDeviceDescription( "Sprayer01.XML" ) == 0) {
  // after  the device value presentation has changed to English
  // the designators are changed too
  Iso11783IL_PDDChangeDesignator ( 1, "Tank volume" );
  Iso11783IL_PDDChangeDesignator ( 2, "App rate per area" );
} else {
  write( "Error while update file" );
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
