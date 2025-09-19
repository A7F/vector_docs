[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSetOutputMode.md)

**CAPL Functions** » **VT System** » **vtsSetOutputMode**

# vtsSetOutputMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long vtsSetOutputMode (char Target[], eVTS2848OutputMode Mode);
```

## Description

Sets the mode for output on the channel.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **Mode**: Modes of VT2848 module: Values see [eVTS2848OutputMode](../CAPLfunctionsVTSystemEnumeration.md#eVTS2848OutputMode)

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified mode is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

The following example demonstrates how to use the PWM output of a VT2848 channel to simulate a PWM based sensor (e.g. a RPM sensor). The channel used in this example is called **RPM_Sensor**.

### CAPL

```plaintext
SimulateSensorPWM ()
{
  // The current value of the frequency (100Hz)
  float currentFrequency = 100.0;

  // Choose ′low side switch′, PWM curve type and
  // Vext as source for high value
  vtsSetOutputMode ("VTS::RPM_Sensor", eVTS2848OutputModeLowsideSwitch);
  vtsSetCurveType("VTS::RPM_Sensor", eVTSCurveTypePWM);
  vtsSetOutputSource("VTS::SensorModule1", eVTSOutputSourceGroupChannels1To4, eVTSOutputSourceVExt);

  // Set the number of repeats to unlimited
  vtsSetPWMRepeats("VTS::RPM_Sensor", 0);

  // Set initial frequency (100Hz) and duty cycle (50%) values
  @sysvar::VTS::RPM_Sensor::PWMOutputFreq = currentFrequency;
  @sysvar::VTS::RPM_Sensor::PWMOutputDC = 50.0;

  // Start the stimulation
  vtsStartStimulation("VTS::RPM_Sensor");

  // To stimulate different sensor readings increase
  // frequency of the PWM signal over time
  while(currentFrequency < 200)
  {
    // Increase the frequency by 1Hz every 100ms
    TestWaitForTimeOut(100);
    currentFrequency += 1;
    @sysvar::VTS::RPM_Sensor::PWMOutputFreq = currentFrequency;
  }

  // Stop the stimulation
  StopStimulation();
}
```

### .NET (C#)

```csharp
public void SimulateSensorPWM()
{
    // Get VTS interface, module and channel
    IVTSystem vts = VTSystem.Instance;
    IVT2848 sensorModule1 = vts.GetChannel<IVT2848>("Sensor_Module1");
    IVT2848PWMStimChannel rpmSensor = vts.GetChannel<IVT2848PWMStimChannel>("RPM_Sensor");

    // The current value of the frequency (100Hz)
    double currentFrequency = 100.0;

    // Choose the source for high voltage on channels 1-4
    sensorModule1.OutputSource1To4.Value = OutputSource.VExt;

    // Choose a PWM curve
    rpmSensor.CurveType.Value = CurveType.PWM;
    // Set the number of repeats to unlimited
    rpmSensor.PWMRepeats.Value = 0;

    // Set initial frequency (100Hz) and duty cycle (50%) values
    rpmSensor.PWMOutputFreq.Value = currentFrequency;
    rpmSensor.PWMOutputDC.Value = 50.0;

    // Start the stimulation
    rpmSensor.StartStimulation();

    // To stimulate different sensor readings increase
    // frequency of the PWM signal over time
    while (currentFrequency < 200)
    {
        // Increase the frequency by 1Hz every 100ms
        Vector.CANoe.Threading.Execution.Wait(100);
        currentFrequency += 1;
        rpmSensor.PWMOutputFreq.Value = currentFrequency;
    }

    // Stop the stimulation
    rpmSensor.StopStimulation();
}
```

### [VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md)

- Select **SensorModule1**
- Set **Sidebar** | **Output Sources** | **Channel 1 to 4** to **Vext**
- Select **RPM_Sensor**
- Set **Sidebar** | **Output Settings** | **Output Mode** to **Low side switch**
- Set **Sidebar** | **Output Settings** | **Curve Type** to **PWM**
- Set **Sidebar** | **PWM Output** | **Repeats** to **0**
- Set **Sidebar** | **PWM Output** | **Frequency** to **100.0**
- Set **Sidebar** | **PWM Output** | **Duty Cycle** to **50.0**
- Click **Sidebar** | **Output Settings** | **Start Stimulation**
- Increase PWM frequency in 20Hz steps
- Set **Sidebar** | **PWM Output** | **Frequency** to **120.0**
- Set **Sidebar** | **PWM Output** | **Frequency** to **140.0**
- Set **Sidebar** | **PWM Output** | **Frequency** to **160.0**
- Set **Sidebar** | **PWM Output** | **Frequency** to **180.0**
- Set **Sidebar** | **PWM Output** | **Frequency** to **200.0**
- Click **Sidebar** | **Output Settings** | **Stop Stimulation**

[SetOutputMode](CAPLfunctionVTSSetOutputMode.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
