[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSetThreshold18.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » vtsSetThreshold1_8

# vtsSetThreshold1_8

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long vtsSetThreshold1_8 (char Namespace [], double Threshold);
```

## Description

Sets the threshold value for differentiating between high and low levels of the channels 1…8 of a digital module VT2516. There is only one threshold setting for all eight channels together. Voltages at the input exceeding this threshold value are evaluated as high level and voltages undershooting it are evaluated as low level.

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

The following example demonstrates how to measure a PWM signal on a VT2516 channel (e.g. a ECU output that controls an LED). The measured frequency and duty cycle is then output to the Write Window / the test report.

### CAPL

```capl
PWMMeasurement ()
{
  // Declare variables to hold measured data
  float frequency;
  float dutyCycle;

  // Set threshold for channels 1-8 to 2.5 V
  vtsSetThreshold1_8("VTS::DigitalSignals", 3.5);

  // Set maximum measurement duration to 100 ms
  // (because the lowest PWM frequency is 100 Hz)
  vtsSetPWMMeasurementDuration("VTS::LED", 0.1);

  // Wait 100 ms and read measured PWM parameters
  TestWaitForTimeout (100);
  frequency = @sysvar::VTS::LED::PWMFreq;
  dutyCycle = @sysvar::VTS::LED::PWMDC;

  // Output measured values to the Write Window
  write("Frequency: %0.2fHz, Duty Cycle: %0.2f%%.", frequency, dutyCycle);
}
```

### .NET (C#)

```csharp
public void PWMMeasurement()
{
    // Get VTS interface, VT2516 module and VT2516 channel
    IVTSystem vts = VTSystem.Instance;
    IVT2516 vt2516 = vts.GetModule("DigitalSignals") as IVT2516;
    IVT2516Channel led = vts.GetChannel("LED") as IVT2516Channel;
    // Set threshold for channels 1-8 to 2.5 V
    vt2516.Threshold1To8.Value = 3.5;

    // Set maximum measurement duration to 100 ms
    // (because the lowest PWM frequency is 100 Hz)
    led.PWMMeasurementDuration.Value = 0.1;

    // Wait 100 ms and read measured PWM parameters
    Vector.CANoe.Threading.Execution.Wait(100);
    double frequency = led.PWMFreq.Value;
    double dutyCycle = led.PWMDC.Value;

    // Output measured values to the Write Window
    Vector.Tools.Output.WriteLine("Frequency: " + frequency + "Hz");
    Vector.Tools.Output.WriteLine("DutyCycle: " + dutyCycle + "%");
}
```

### VT System Control

[VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md)

- Select **DigitalSignals**
- Set **Sidebar** | **PWM Measurement** | **Threshold 1 to 8** to **3.5**
- Select **LED**
- Set **Sidebar** | **PWM Measurement** | **Meas. Duration** to **0.1**
- Wait for 100ms
- Check measurement values 'PWMFreq' and 'PWMDC'

[SetThreshold1_8](CAPLfunctionVTSSetThreshold18.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)