[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSetPWMMeasurementDuration.md)

## vtsSetPWMMeasurementDuration

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » vtsSetPWMMeasurementDuration

### Valid for: CANoe DE • CANoe:lite DE

### Function Syntax

```plaintext
long vtsSetPWMMeasurementDuration (char Target[], double Duration);
```

### Description

During measurement of PMW Parameters with the Modules VT1004/VT1104, VT2516 or VT2848 a Duty Cicle of 0 or 100% is shown, if during the defined time no edge was recognized. This time is set with **vtsSetPWMMeasurementDuration** ([SetPWMMeasurementDuration](CAPLfunctionVTSSetPWMMeasurementDuration.md)). Usefully, the set time should be greater than the period of the lowest frequency to be measured. So that 0% or 100% duty cycle could be identified as quickly as possible, the time should not be set to too high, because in the meantime the old values are still displayed.

### Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **Duration**: Time window in seconds during which PWM signals are measured.  
  VT1004/VT1104, VT2516 and VT2848: Time windows can be set between 10 ms (0.01) and 1 min (60) in steps of 10 ms.  
  If an invalid value is specified, the setting is rounded up to the next highest value.

### Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified measurement duration is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

### Example

This example demonstrates how to do a PWM measurement on a channel of a VT1004 module. In this example the channel is called **RPMSensor** and assumed to be connected to a sensor which generates a **PWM** signal. Every second the measured frequency and duty cycle are written to the Write Window of the CANoe DE Family/ once to the test report.

#### CAPL

```plaintext
PerformPWMMeasurement ()
{
  // Declare variables to hold measured data
  float frequency;
  float dutyCycle;

  // Configure channel for PWM measurement
  vtsSetPWMMeasurementDuration("VTS::RPMSensor", 0.1); // 100ms
  vtsSetPWMThreshold("VTS::RPMSensor", 2.5);           // 2.5V

  // Print measurement results to Write Window every second
  while(1)
  {
    // Get measured values from VT System system variables
    frequency = @sysvar::VTS::RPMSensor::PWMFreq;
    dutyCycle = @sysvar::VTS::RPMSensor::PWMDC;

    write("Frequency: %0.2fHz, Duty Cycle: %0.2f%%.", frequency, dutyCycle);
    TestWaitForTimeOut(1000);
  }
}
```

#### .NET (C#)

```csharp
public void PerformPWMMeasurement()
{
    // Get VTS interface and VT1004 channel
    IVTSystem vts = VTSystem.Instance;
    IVT1004Channel rpmSensor = vts.GetChannel("RPMSensor") as IVT1004Channel;

    // Configure channel for PWM measurement
    rpmSensor.PWMMeasurementDuration.Value = 0.1; // 100ms
    rpmSensor.PWMThreshold.Value = 2.5; // 2.5V

    // Print measurement results to Write Window every second
    while (true)
    {
        Vector.Tools.Output.WriteLine("Frequency: " + rpmSensor.PWMFreq.Value + "Hz");
        Vector.Tools.Output.WriteLine("DutyCycle: " + rpmSensor.PWMDC.Value + "%");
        Vector.CANoe.Threading.Execution.Wait(1000);
    }
}
```

#### [VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md)

Select **RPMSensor**  
Set **Sidebar** | **PWM Measurement** | **Meas. Duration** to **0.1**  
Set **Sidebar** | **PWM Measurement** | **Threshold** to **2.5**  
Check measurement values 'PWMFreq' and 'PWMDC'

[SetPWMMeasurementDuration](CAPLfunctionVTSSetPWMMeasurementDuration.md)
