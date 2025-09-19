[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetPWMVoltageHigh.md)

**CAPL Functions** » **VT System** » **SetPWMVoltageHigh**

# SetPWMVoltageHigh

**Valid for**: CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces of appropriate channels of **VT System** modules.

## Method Syntax

`long SysVarNamespace.SetPWMVoltageHigh (double Voltage);`

## Description

Specifies the high level on output of a digital output signal, especially a PWM signal.

## Parameters

- **Voltage**: Voltage of the low level in volts in the range 0 ... 27 V (**VT2004**), 0... 40V (**VT2004A**) resp. 0 ... 25 V (**VT2516**).

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.
- **-3**: The specified voltage is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

See example [SetStimulationMode](CAPLfunctionVTSSetStimulationMode.md)

[vtsSetPWMVoltageHigh](CAPLfunctionVTSvtsSetPWMVoltageHigh.md)

© Vector Informatik GmbH  
**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
