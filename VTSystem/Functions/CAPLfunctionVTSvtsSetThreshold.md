# vtsSetThreshold

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSetThreshold.md)

**CAPL Functions** » **VT System** » **vtsSetThreshold**

## Function Syntax

```plaintext
long vtsSetThreshold (char Target[], dword Group, double Threshold);
```

## Description

Sets the threshold value for differentiating between high and low levels of a group of channels on a **VT2848** module. There is only one threshold setting for each group. Voltages at the input exceeding this threshold value are evaluated as high level and voltages undershooting it are evaluated as low level.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **Group**: Values see [eVTSThresholdGroup](../CAPLfunctionsVTSystemEnumeration.md#eVTSThresholdGroup)
- **Threshold**: Voltage value in volts in the range from 0…40 V.

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.
- **-3**: The specified threshold is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the **VT System**. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

The following example demonstrates how to configure the first channel of a VT2848 module for PWM measurement. The channel used in this example is called **RPM_Sensor**, the **VT2848** is called **Sensors**.

### CAPL

```plaintext
PWMMeasurement ()
{
  // Set the PWM thresholds of channels 1 to 8 to 2.5V
  vtsSetThreshold("Sensors", eVTSThresholdGroupChannels1To8, 2.5);

  // Set the PWM measurement duration of the first channel to 100ms
  vtsSetPWMMeasurementDuration("RPM_Sensor", 0.1);

  // Wait 500ms and output the measured PWM frequency and duty cycle
  TestWaitForTimeout(500);
  write("Measured frequency %fHz and DC %f", @sysvar::VTS::RPM_Sensor::PWMFreq, @sysvar::VTS::RPM_Sensor::PWMDC);
}
```

### .NET (C#)

```csharp
private void Example3()
{
    IVTSystem vts = VTSystem.Instance;
    // Get the VT2848 module
    IVT2848 sensors = vts.GetModule<IVT2848>("Sensors");

    // Set the PWM thresholds of channels 1 to 8 to 2.5V
    sensors.Threshold1To8.Value = 2.5;

    // Set the PWM measurement duration of the first channel to 100ms
    sensors.Channel1.PWMMeasurementDuration.Value = 0.1;

    // Wait 500ms and output the measured PWM frequency and duty cycle
    Execution.Wait(500);
    Output.WriteLine(string.Format("Measured frequency {0}Hz and DC {0}%", sensors.Channel1.PWMFreq.Value, sensors.Channel1.PWMDC.Value));
}
```

### VT System Control

- Select **Sensors**
- Set **Sidebar** | **Thresholds** | **Channel 1 to 8** to **2.5**
- Select **RPM_Sensor**
- Set **Sidebar** | **PWM Measurement** | **Meas. Duration** to **0.1**
- Wait for 500ms
- Check measurement values 'PWMFreq' and 'PWMDC'

[SetThreshold](CAPLfunctionVTSSetThreshold.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
