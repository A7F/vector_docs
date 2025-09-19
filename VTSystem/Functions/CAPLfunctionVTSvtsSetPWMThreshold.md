[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSetPWMThreshold.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » vtsSetPWMThreshold

# vtsSetPWMThreshold

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long vtsSetPWMThreshold (char Target[], double Threshold);
```

## Description

Sets the threshold value for differentiating between high and low levels. Voltages at the input exceeding this threshold value are evaluated as high level and voltages undershooting it are evaluated as low level.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **Threshold**:
  - **Comparison Table**:
    - **VT1004**: -32 V to +32 V
    - **VT1004A**: -40 V to +40 V
    - **VT1104**: -60 V to +60 V

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified threshold is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

See example [vtsSetPWMMeasurementDuration](CAPLfunctionVTSvtsSetPWMMeasurementDuration.md)

[SetPWMThreshold](CAPLfunctionVTSSetPWMThreshold.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
