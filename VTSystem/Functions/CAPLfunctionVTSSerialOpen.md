[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSerialOpen.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » SerialOpen

# SerialOpen

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces of channels that represent an external power supply in a power module VT7001 respectively the system variable namespace that represents functionality common for the entire VT7001 module.  
To make sure that no data is lost execute a wait command between the call of this function and the following sending or receiving of data.

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax  
`SysVarNamespace.SerialOpen();`

## Description

Opens the serial port of the VT System channel that is specified by the system variable namespace.

## Parameters

—

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.

## Example

See example [SerialConfigure](CAPLfunctionVTSSerialConfigure.md)

[vtsSerialOpen](CAPLfunctionVTSvtsSerialOpen.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
