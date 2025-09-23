[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSetThreshold916.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » vtsSetThreshold9_16

# vtsSetThreshold9_16

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long vtsSetThreshold9_16 (char Namespace[], double Threshold);
```

## Description

Sets the threshold value for differentiating between high and low levels of the channels 9…16 of a digital module VT2516. There is only one threshold setting for all eight channels together. Voltages at the input exceeding this threshold value are evaluated as high level and voltages undershooting it are evaluated as low level.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **Threshold**: Voltage value in volts in the range from 0…25 V.

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified threshold is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

See example [vtsSetThreshold1_8](CAPLfunctionVTSvtsSetThreshold18.md)

[SetThreshold9_16](CAPLfunctionVTSSetThreshold916.md)
