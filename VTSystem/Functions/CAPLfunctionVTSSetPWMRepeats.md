[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetPWMRepeats.md)

## SetPWMRepeats

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » SetPWMRepeats

**Valid for:** CANoe DE • CANoe:lite DE

### Note

The function can only be called on system variable namespaces of appropriate channels of VT System modules.

### Method Syntax

`long SysVarNamespace.SetPWMRepeats (dword numOfRepeats);`

### Description

This function sets the number of stimulated PWM periods after the start of stimulation. If the number of cycles output is not limited, **numOfRepeats** must be set to **0**.

### Parameters

- **numOfRepeats**: Number of PWM periods to be stimulated.  
  Valid values: 0…65535.

### Return Values

- **0**: Successful call
- **-1**: Error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified number of repeats is not valid.

### Example

See example [SetStimulationMode](CAPLfunctionVTSSetStimulationMode.md)

[vtsSetPWMRepeats](CAPLfunctionVTSvtsSetPWMRepeats.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)