[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetPWMThreshold.md)

**CAPL Functions** » **VT System** » **SetPWMThreshold**

# SetPWMThreshold

**Valid for**: CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces of channels belonging to the **VT System** module **VT1004** or **VT1104**.

## Method Syntax

`long SysVarNamespace.SetPWMThreshold (double Threshold);`

## Description

Sets the threshold value for differentiating between high and low levels. Voltages at the input exceeding this threshold value are evaluated as high level and voltages undershooting it are evaluated as low level.

## Parameters

- **Threshold**

  | Comparison Table | VT1004          | VT1004A         | VT1104          |
  |------------------|-----------------|-----------------|-----------------|
  | Voltage value in volts in the range from ... | -32 V to +32 V | -40 V to +40 V | -60 V to +60 V |

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.
- **-3**: The specified threshold is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

See example [SetPWMMeasurementDuration](CAPLfunctionVTSSetPWMMeasurementDuration.md)

[vtsSetPWMThreshold](CAPLfunctionVTSvtsSetPWMThreshold.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
