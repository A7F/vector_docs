[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSerialOpen.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » vtsSerialOpen

# vtsSerialOpen

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**  
To make sure that no data is lost execute a wait command between the call of this function and the following sending or receiving of data.

## Function Syntax

`long vtsSerialOpen (char Target[]);`

## Description

Opens the serial port of the VT System channel that is specified by the system variable namespace.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.

## Example

See example [vtsSerialConfigure](CAPLfunctionVTSvtsSerialConfigure.md)

[SerialOpen](CAPLfunctionVTSSerialOpen.md)
