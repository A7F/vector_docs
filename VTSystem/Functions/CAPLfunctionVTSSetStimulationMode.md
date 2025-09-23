[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetStimulationMode.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » SetStimulationMode

# SetStimulationMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note:** The function can only be called on system variable namespaces of appropriate channels of VT System modules.

## Method Syntax

```plaintext
long SysVarNamespace.SetStimulationMode (eVTSStimulationMode Mode);
```

## Description

Sets the mode for internal voltage or resistance stimulation.

## Parameters

- **Mode**: Values see [eVTSStimulationMode](../CAPLfunctionsVTSystemEnumeration.md#eVTSStimulationMode)

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified mode is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise, the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

The following example demonstrates how to use the PWM output of a VT2004 channel to simulate a PWM based sensor (e.g., a RPM sensor). The channel used in this example is called **RPM_Sensor**.

### CAPL

```plaintext
SimulateSensorPWM ()
{
  // The current value of the frequency (100Hz)
  float currentFrequency = 100.0;

  // Choose voltage stimulation and a PWM curve type
  sysvar::VTS::RPM_Sensor.SetStimulationMode(eVTSStimulationModeVoltage);
  sysvar::VTS::RPM_Sensor.SetCurveType(eVTSCurveTypePWM);

  // PWM signal will toggle between 0V and 5V
  sysvar::VTS::RPM_Sensor.SetPWMVoltageLow(0.0);
  sysvar::VTS::RPM_Sensor.SetPWMVoltageHigh(5.0);

  // Set the number of repeats to unlimited
  sysvar::VTS::RPM_Sensor.SetPWMRepeats(0);

  // Set initial frequency (100Hz) and duty cycle (50%) values
  @sysvar::VTS::RPM_Sensor::PWMFreq = currentFrequency;
  @sysvar::VTS::RPM_Sensor::PWMDC = 50.0;

  // Start the stimulation
  sysvar::VTS::RPM_Sensor.StartStimulation();

  // To stimulate different sensor readings increase
  // frequency of the PWM signal over time
  while(currentFrequency < 200)
  {
    // Increase the frequency by 1Hz every 100ms
    TestWaitForTimeOut(100);
    currentFrequency += 1;
    @sysvar::VTS::RPM_Sensor::PWMFreq = currentFrequency;
  }

  // Stop the stimulation
  sysvar::VTS::RPM_Sensor.StopStimulation();
}
```

### .NET (C#)

```csharp
public void SetRefVoltageMode()
{
  // Get VTS interface, VT7001 module, internal supply and a output channel
  IVTSystem vts = VTSystem.Instance;
  IVT7001 powerSupply = vts.GetModule("PowerSupply") as IVT7001;
  IVT7001SupplyExternal extSupply = vts.GetChannel("ExtSupply") as IVT7001SupplyExternal;
  IVT7001Channel clamp30 = vts.GetChannel("Clamp30") as IVT7001Channel;

  // Set mode to one power supply only -> external power supply 1
  powerSupply.InterconnectionMode.Value = InterconnectionMode.Sup1;

  // Activate the reference voltage mode with constant value mode
  // and a factor of 0.1
  extSupply.SetRefVoltageMode(RefVoltageMode.Constant, 0.1);

  // The following line sets the output voltage to 15 V,
  // VControl (1.5 V) is calculated with the given factor automatically
  extSupply.RefVoltage.Value = 15.0;

  // Switch output on
  clamp30.Active.Value = OutputMode.Active;
}
```

### [VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md)

- Select **RPM_Sensor**
- Set **Sidebar** | **General** | **Stim Mode** to **Voltage**
- Set **Sidebar** | **General** | **Curve Type** to **PWM**
- Set **Sidebar** | **PWM Output** | **Voltage High** to **5.0**
- Set **Sidebar** | **PWM Output** | **Voltage Low** to **0.0**
- Set **Sidebar** | **PWM Output** | **Parameters | Repeats** to **0**
- Set **Sidebar** | **PWM Output** | **Frequency** to **100.0**
- Set **Sidebar** | **PWM Output** | **Duty Cycle** to **50.0**
- Click **Sidebar** | **General** | **Start Stimulation**
- Increase frequency
- Set **Sidebar** | **PWM Output** | **Frequency** to **200.0**

[vtsSetStimulationMode](CAPLfunctionVTSvtsSetStimulationMode.md)
