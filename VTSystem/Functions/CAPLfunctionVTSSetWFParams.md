[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetWFParams.md)

**CAPL Functions** » **VT System** » **SetWFParams**

# SetWFParams

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**: The function can only be called on system variable namespaces of appropriate channels of VT System modules.

## Method Syntax

- `long SysVarNamespace.SetWFParams (double timeIncrement, double pause, dword numOfRepeats)` // form 1
- `long SysVarNamespace.SetWFParams (double timeIncrement, double pause, dword numOfRepeats, double startDelay, dword startPoint)` // form 2

## Description

The function configures the parameters for the output of a voltage or resistance curve or bitstream.

## Parameters

- **timeIncrement**: Specifies how long the value of a specified interpolation point is to be stimulated before transitioning to the next interpolation point. Depending on the module and the waveform, different ranges for `timeIncrement` are valid:
  - Voltage curves on a **VT7001** module: `timeIncrement` can be 0.000001(1 µs)…0.065 (65 ms).
  - Voltage curves on a **VT2816** or **VT2004** module: `timeIncrement` can be -0.065 (-65 ms)…0.065 (65 ms).
  - Resistance curves: 0.0005 (500 µs)…0.065 (65 ms) in **R\>** mode and 0.001 (1 ms)…0.065 (65 ms) in **R\<** mode.
  - BitStreams on a **VT2516** module: `timeIncrement` can be 0.000002 (2 µs)…0.065 (65 ms).
  - BitStreams on a **VT2848** module: `timeIncrement` can be -0.065 (-65 ms)…0.065 (65 ms).

- **pause**: Specifies how long the stimulation is interrupted between two repetitions of the waveform. Valid values: 0.0…4294.0 (4294 s).

- **numOfRepeats**: Specifies how many times in a row the curve is to be stimulated. Valid values: 0…65535 (0 means unlimited repetition of the curve).

- **startDelay**: Specifies a delay for the start of the stimulation in seconds. This parameter is only supported by the **VT2004**, **VT2816**, and **VT2848** modules. Valid values: 0.0..4.0 (4 s).

- **startPoint**: Specifies the point of the stimulated curve the stimulation should begin with. This parameter is only supported by the **VT2004**, **VT2816**, and **VT2848** modules. Valid values: 0..4096

## Return Values

- **0**: Successful call
- **-1**: Error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace, or does not support this command.
- **-3**: One of the specified parameters is not valid.

## Example

The following example demonstrates how to use the waveform resistance output of a **VT2004** channel to simulate a sensor. In the example, a waveform called **WaveForm.TXT** is loaded and replayed on channel **Temp_Sensor**.

### Example WaveForm.TXT

```plaintext
// Example of an arbitrary wave form for resistance stimulation
100
120 ; 2
140 ; 1
100
160 ; 4
100
```

### CAPL

```plaintext
SimulateSensorResistanceWF ()
{
  // Choose resistor stimulation and waveform curve type
  sysvar::VTS::Temp_Sensor.SetStimulationMode(3);
  sysvar::VTS::Temp_Sensor.SetCurveType(2);

  // Load waveform (the contents of waveform.TXT are listed below)
  sysvar::VTS::Temp_Sensor.LoadWFResistance("C:\\WaveForm.TXT");

  // Configure waveform. Parameters:
  // TimeIncrement (time to hold each sample)        = 65ms
  // Pause (pause between two waveform repetitions) = 2s
  // NumberOfRepeats (number of repetitions)         = 3
  sysvar::VTS::Temp_Sensor.SetWFParams(0.065, 2.0, 3);

  // Start stimulation with the previously configured waveform
  sysvar::VTS::Temp_Sensor.StartStimulation();
}
```

### .NET (C#)

```csharp
public void SimulateSensorResistanceWF()
{
    // Get VTS interface and VT2004 channel
    IVTSystem vts = VTSystem.Instance;
    IVT2004Channel tempSensor = vts.GetChannel("Temp_Sensor") as IVT2004Channel;

    // Choose voltage stimulation and a constant curve type
    tempSensor.SetStimulationMode(StimulationMode.ResistanceLower, CurveType.AnalogWaveform);

    // Load waveform (the contents of waveform.TXT are listed below)
    tempSensor.LoadWFResistance("C:\\WaveForm.TXT");

    // Configure waveform. Parameters:
    // TimeIncrement (time to hold each sample)        = 65ms
    // Pause (pause between two waveform repetitions) = 2s
    // NumberOfRepeats (number of repetitions)         = 3
    tempSensor.SetWFParams(0.065, 2.0, 3);

    // Start stimulation with the previously configured waveform
    tempSensor.StartStimulation();
}
```

### VT System Control

Select **Temp_Sensor**  
Set **Sidebar** | **General** | **Stim Mode** to **R**  
Set **Sidebar** | **General** | **Curve Type** to **Constant**  
Set **Sidebar** | **Waveform Output** | **WF Resistance** to **WaveForm.txt**  
Set **Sidebar** | **Waveform Output** | **Parameters | Time Increment** to **0.065**  
Set **Sidebar** | **Waveform Output** | **Parameters | Pause** to **2.0**  
Set **Sidebar** | **Waveform Output** | **Parameters | Repeats** to **3**  
Click **Sidebar** | **General** | **Start Stimulation**

[vtsSetWFParams](CAPLfunctionVTSvtsSetWFParams.md)
