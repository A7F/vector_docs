[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSLoadWFVoltage.md)

**CAPL Functions** » **VT System** » **LoadWFVoltage**

# LoadWFVoltage

**Valid for**: CANoe DE • CANoe:lite DE

**Note**  
The method can only be called on system variable namespaces of appropriate channels of **VT System** modules.  
The method may not be called in any CAPL handler routines or in ECU nodes. It may only be called in the context of the MainTest method of a test module.

## Method Syntax

```plaintext
long SysVarNamespace.LoadWFVoltage (char filepath[]);
```

## Description

The function loads a voltage curve for the channel from the specified file.

## Parameters

- **filepath**: Path of the file containing the voltage curve. The path can be given absolute or relative to the CANoe DE Family configuration.

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.
- **-3**: Error when accessing the file. This can mean, for example, that the file was not found or the file format was different than expected.
- **-4**: Transfer error – The wave form could not be transferred correctly.

## Example

The following example demonstrates how to use the waveform voltage output of a **VT2004** channel to simulate a sensor. In the example a waveform called **WaveForm.TXT** is loaded and replayed on channel **Temp_Sensor**. More details on waveforms can be found on CANoe DE Family help topic [VT2004: Arbitrary Wave Forms](../../../CANoeCANalyzer/VTSystem/VT2004/VT2004ArbitraryWaveForms.md).

The second part of the example shows how a waveform can be output on a **VT7001** power supply channel. An external power supply unit (namespace **ExtSupply**) is used in this example. The ECU is connected to **OUT1** (namespace **ECUpower**) and **GND1**; the **VT7001** module is named **Power-Supply**. The output voltage is determined by a predefined curve (**powercycle.TXT**). The time increment for the curve's interpolation points is 65 ms; the curve is for 10 seconds.

### Example WaveForm.TXT

```plaintext
// Example of an arbitrary wave form
0 // Next value is an interpolation point
1.0; 2 // Two sampling points lie between the next interpolation point
4
2 // Also possible
3; 1
1; 1
2
```

### CAPL

```plaintext
SimulateSensorVoltageWF ()
{
  // Choose voltage stimulation and waveform curve type
  sysvar::VTS::Temp_Sensor.SetStimulationMode(1);
  sysvar::VTS::Temp_Sensor.SetCurveType(2);

  // Load waveform (the contents of WaveForm.TXT are listed below)
  sysvar::VTS::Temp_Sensor.LoadWFVoltage("C:\\WaveForm.TXT");

  // Configure waveform. Parameters:
  // TimeIncrement (time to hold each sample)      = 65ms
  // Pause (pause between two waveform repetitions) = 2s
  // NumberOfRepeats (number of repetitions)       = 0 (unlimited)
  sysvar::VTS::Temp_Sensor.SetWFParams(0.065, 2.0, 0);

  // Output the configured waveform for 10 seconds
  sysvar::VTS::Temp_Sensor.StartStimulation();
  TestWaitForTimeout(10000);
  sysvar::VTS::Temp_Sensor.StopStimulation();
}

ExternalSupplyWithCurve ()
{
  // Set mode to one power supply only -> external power supply 1
  sysvar::VTS::PowerSupply.SetInterconnectionMode(1);

  // Load waveform from file
  // Factor is set to 0.2: 1 V control voltage -> 5 V output at power supply
  sysvar::VTS::ExtSupply.SetRefVoltageMode(2, 0.2);
  sysvar::VTS::ExtSupply.LoadWFVoltage("powercycle.TXT");
  sysvar::VTS::ExtSupply.SetWFParams(0.00005, 0.2, 0);

  // Switch outputs on and start output curve
  @sysvar::VTS::Clamp30::Active = 1;
  sysvar::VTS::ExtSupply.StartStimulation();

  // Wait for 5 seconds, the stop the curve playback
  TestWaitForTimeOut(5000);
  sysvar::VTS::ExtSupply.StopStimulation();
}
```

### .NET (C#)

```csharp
public void SimulateSensorVoltageWF()
{
    // Get VTS interface and VT2004 channel
    IVTSystem vts = VTSystem.Instance;
    IVT2004Channel tempSensor = vts.GetChannel("Temp_Sensor") as IVT2004Channel;

    // Choose voltage stimulation and a constant curve type
    tempSensor.SetStimulationMode(StimulationMode.Voltage, CurveType.AnalogWaveform);

    // Load waveform (the contents of waveform.TXT are listed below)
    tempSensor.LoadWFVoltage("C:\\WaveForm.TXT");

    // Configure waveform. Parameters:
    // TimeIncrement (time to hold each sample)      = 65ms
    // Pause (pause between two waveform repetitions) = 2s
    // NumberOfRepeats (number of repetitions)       = 0 (unlimited)
    tempSensor.SetWFParams(0.065, 2.0, 0);

    // Output the configured waveform for 10 seconds
    tempSensor.StartStimulation();
    Vector.CANoe.Threading.Execution.Wait(10000);
    tempSensor.StopStimulation();
}

public void ExternalSupplyWithCurve()
{
    // Get VTS interface, VT7001 module, external supply and output channel
    IVTSystem vts = VTSystem.Instance;
    IVT7001 powerSupply = vts.GetModule("PowerSupply") as IVT7001;
    IVT7001SupplyExternal extSupply = vts.GetChannel("ExtSupply") as IVT7001SupplyExternal;
    IVT7001Channel clamp30 = vts.GetChannel("Clamp30") as IVT7001Channel;

    // Set mode to one power supply only -> external power supply 1
    powerSupply.InterconnectionMode.Value = InterconnectionMode.Sup1;

    // Load waveform from file
    // Factor is set to 0.2: 1 V control voltage -> 5 V output at power supply
    extSupply.SetRefVoltageMode(RefVoltageMode.AnalogWaveForm, 0.2);
    extSupply.LoadWFVoltage("powercycle.TXT");
    extSupply.SetWFParams(0.00005, 0.2, 0);

    // Switch outputs on and start output curve
    clamp30.Active.Value = OutputMode.Active;
    extSupply.StartStimulation();

    // Wait for 5 seconds, the stop the curve playback
    Vector.CANoe.Threading.Execution.Wait(5000);
    extSupply.StopStimulation();
}
```

### [VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md)

Select **Temp_Sensor**  
Set **Sidebar** | **General** | **Stim Mode** to **Active**  
Set **Sidebar** | **General** | **Curve Type** to **Waveform**  
Set **Sidebar** | **Waveform Output** | **WF Voltage** to **Waveform.txt**  
Set **Sidebar** | **Waveform Output** | **Parameters | Time Increment** to **0.065**  
Set **Sidebar** | **Waveform Output** | **Parameters | Pause** to **2.0**  
Set **Sidebar** | **Waveform Output** | **Parameters | Repeats** to **0**  
Click **Sidebar** | **General** | **Start Stimulation**  
Wait for 10 seconds  
Click **Sidebar** | **General** | **Stop Stimulation**

[vtsLoadWFVoltage](CAPLfunctionVTSvtsLoadWFVoltage.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
