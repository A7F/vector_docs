[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILpddloaddevicedescription.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_PDDLoadDeviceDescription

# Iso11783IL_PDDLoadDeviceDescription

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
In case the corresponding node is running in the distributed environment, the machine configuration file has to be registered under **File|Options|Extensions|User Files** in CANoe.  
The ISO11783 Interaction Layer allows the [segmented transmission of device descriptions](../../../../CANoeCANalyzer/ISO11783/processData/ProcessDataSegmentedTransmission.md).

## Function Syntax

```plaintext
long Iso11783IL_PDDLoadDeviceDescription( char ddopPath[] ); // form 1
long Iso11783IL_PDDLoadDeviceDescription( char ddopPath[], dword options ); // form 2
long Iso11783IL_PDDLoadDeviceDescription( dbNode implement, char ddopPath[] ); // form 3
long Iso11783IL_PDDLoadDeviceDescription( dbNode implement, char ddopPath[], dword options ); // form 4
```

## Description

The function (form 1 or 3) creates a process data dictionary from a valid device descriptor object pool file (XML) and transfers the device descriptor object pool to the Task Controller. The process variables and properties can be accessed via CAPL functions.

To load and transfer a file with a device descriptor object pool **without checking it for validity**, you must use form 2 or 4 and set the **options** to 1. The **ddopPath** must no longer point to an XML file, but to a **binary file**. In this case, the content of the DDOP file is not validated, no process data dictionary is created and you cannot access process variables or properties via CAPL functions. The content of the binary file is placed in the **Object Pool Transfer** message from the second byte onwards.

## Parameters

- **ddopPath**: File path of the device descriptor object pool (DDOP) file.
- **implement**: Simulation node to apply the function.
- **options**:
  - 1: Load binary representation of a device descriptor object pool. The content of the DDOP file is not validated, no process data dictionary is created and you cannot access process variables or properties via CAPL functions.

## Return Values

- **0**: process data dictionary has been created successfully
- **< 0**: an error has occurred

## Example

```plaintext
if (Iso11783IL_PDDLoadDeviceDescription( "Sprayer.XML" ) == 0) {
  Iso11783IL_PDDConnectSysVar ( 0x0060, 1, "EvSprayer_TankVolume" );
  Iso11783IL_PPDDConnectSysVar ( 0x0048, 2, "EvSprayer_AppRatePerArea" );
}
else {
  write( "Error while load task file" );
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
