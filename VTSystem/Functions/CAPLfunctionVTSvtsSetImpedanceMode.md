[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSetImpedanceMode.md)

## CAPL Functions » VT System » vtsSetImpedanceMode

### vtsSetImpedanceMode

**Valid for:** CANoe DE • CANoe:lite DE

**Note:** The function can only be called on system variable namespaces of appropriate channels of VT System modules. This function is only supported by the VT1004A variant and the VT1104 module.

### Function Syntax

```plaintext
long vtsSetImpedanceMode (char Target[], eVTSImpedanceMode Mode);
```

### Description

Switches for VT1004A/VT1104 between the mode with high impedance (default state) and low impedance. The behavior of a channel in mode with high impedance is the same as the behavior of a channel in older VT1004 modules. In the mode with lower impedance the accurateness of the measurement of PWM frequency and duty cycle. This provides significant advantages especially for measurement of very low or high duty cycles. The input resistance is lower in this mode and thus the load on ECU output is higher.

### Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **Mode**: Sets the active impedance mode. Values see [eVTSImpedanceMode](../CAPLfunctionsVTSystemEnumeration.md#eVTSImpedanceMode)

### Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified mode is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.
- **-6**: The function is not supported by the used variant of the module.

### Example

**PWM measurement with switching of the impedance mode.**

#### CAPL

```plaintext
double frequency;
double dutyCycle;

// Set PWM threshold to 12V
vtsSetPWMThreshold( "LowBeamLeft", 12);
// Set PWM measurement duration to 100ms
vtsSetPWMMeasurementDuration( "LowBeamLeft", 0.1);
// Enable low impedance mode to improve PWM measurement accuracy
vtsSetImpedanceMode( "LowBeamLeft", eVTSImpedanceModeLow);

// Wait a bit until the PWM measurement has finished
testWaitForTimeout(200);

// Get measured values
frequency = @sysvar::VTS::LowBeamLeft::PWMFreq;
dutyCycle = @sysvar::VTS::LowBeamLeft::PWMDC;

// Check the frequency and duty cycle
if( frequency > 50 && dutyCycle > 20 )
{
    testStepPass();
}
else
{
    testStepFail();
}
```

#### .NET (C#)

—

#### [VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md)

Select **LowBeamLeft**

Set **Sidebar** | **PWM Measurement** | **Threshold** to **12.0**  
Set **Sidebar** | **PWM Measurement** | **Meas. Duration** to **0.1**  
Set **Sidebar** | **General** | **Impedance** to **Low**  
Check measurement values 'PWMFreq' and 'PWMDC'

[SetImpedanceMode](CAPLfunctionVTSSetImpedanceMode.md)

---

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)