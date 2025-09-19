[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetPWMStartDelay.md)

## SetPWMStartDelay

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » SetPWMStartDelay

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

### Note

The function can only be called on system variable namespaces of appropriate channels of VT System modules.

### Method Syntax

Long SysVarNamespace.SetPWMStartDelay (double StartDelay);

### Description

Sets the delay of the start for the output of PWM signals and curves. This function is supported by the modules VT2004 and VT2848.

### Parameters

- **StartDelay**: Time for that the start of PWM or curve output is delayed. This function can be used e.g. to put out several signals with a defined phase shift. The StartDelay is denoted in seconds. Allowed values are from 0.0...4.0 (4s). This parameter is transferred to the VT System with nanosecond resolution.

### Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified StartDelay is not valid
- **-6**: The function is not supported by the used variant of the module.

### Example

In the following example the PWM output of two VT2004 channels is simulating two sensors with PWM output. The **SetPWMStartDelay** command ensures that the PWM output on channel **Sensor2** is starting 2ms later to produce the corresponding phase shift.

#### CAPL

```plaintext
// Set up PWM stimulation for sensor 1

// Set voltage stimulation mode
sysvar::VTS::Sensor1.SetStimulationMode(1);
// Set curve type PWM
sysvar::VTS::Sensor1.SetCurveType(1);
// Set the low voltage of the PWM signal to 10V
sysvar::VTS::Sensor1.SetPWMVoltageLow(10);
// Set the high voltage of the PWM signal to 14V
sysvar::VTS::Sensor1.SetPWMVoltageHigh(14);
// Set duty cycle to 40%
@sysvar::VTS::Sensor1::PWMDC = 40;
// Set frequency to 100Hz
@sysvar::VTS::Sensor1::PWMFreq = 100;

// Set up PWM stimulation for sensor 2

// Set voltage stimulation mode
sysvar::VTS::Sensor2.SetStimulationMode(1);
// Set curve type PWM
sysvar::VTS::Sensor2.SetCurveType(1);
// Set the low voltage of the PWM signal to 10V
sysvar::VTS::Sensor2.SetPWMVoltageLow(10);
// Set the high voltage of the PWM signal to 14V
sysvar::VTS::Sensor2.SetPWMVoltageHigh(14);
// Set duty cycle to 40%
@sysvar::VTS::Sensor2::PWMDC = 40;
// Set frequency to 100Hz
@sysvar::VTS::Sensor2::PWMFreq = 100;

// set a start delay of 2ms for Sensor2
// -> PWM signals have a slight phase shift
sysvar::VTS::Sensor2.SetPWMStartDelay(0.02);

// Start stimulation
sysvar::VTS::Sensor1.StartStimulation();
sysvar::VTS::Sensor2.StartStimulation();
```

[vtsSetPWMStartDelay](CAPLfunctionVTSvtsSetPWMStartDelay.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
