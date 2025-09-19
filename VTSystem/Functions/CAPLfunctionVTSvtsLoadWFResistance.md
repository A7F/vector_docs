[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsLoadWFResistance.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » vtsLoadWFResistance

# vtsLoadWFResistance

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE

**Note**  
The function may not be called in any CAPL handler routines or in ECU nodes. It may only be called in the context of the MainTest method of a test module.

## Function Syntax

`long vtsLoadWFResistance (char Target[], char filepath[]);`

## Description

This function loads a resistance curve for a VT2004 channel from the specified file.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **filepath**: Path of the file containing the resistance curve. The path can be given absolute or relative to the CANoe DE Family configuration.

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: Error when accessing the file. This can mean, for example, that the file was not found or the file format was different than expected.
- **-4**: Transfer error – The wave form could not be transferred correctly.

## Example

See example [vtsSetWFParams](CAPLfunctionVTSvtsSetWFParams.md)

[LoadWFResistance](CAPLfunctionVTSLoadWFResistance.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
