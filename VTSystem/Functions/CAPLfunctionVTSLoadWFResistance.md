[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSLoadWFResistance.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » LoadWFResistance

# LoadWFResistance

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**

The method can only be called on system variable namespaces of channels belonging to the VT System module VT2004. The method may not be called in any CAPL handler routines or in ECU nodes. It may only be called in the context of the MainTest method of a test module.

## Method Syntax

`long SysVarNamespace.LoadWFResistance (char filepath[]);`

## Description

This function loads a resistance curve for a VT2004 channel from the specified file.

## Parameters

- **filepath**: Path of the file containing the resistance curve. The path can be given absolute or relative to the CANoe DE Family configuration.

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: Error when accessing the file. This can mean, for example, that the file was not found or the file format was different than expected.
- **-4**: Transfer error – The wave form could not be transferred correctly.

## Example

See example [SetWFParams](CAPLfunctionVTSSetWFParams.md)

[vtsLoadWFResistance](CAPLfunctionVTSvtsLoadWFResistance.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
