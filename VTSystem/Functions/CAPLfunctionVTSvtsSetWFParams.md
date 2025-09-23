[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSetWFParams.md)

**CAPL Functions** » **VT System** » **vtsSetWFParams**

# vtsSetWFParams

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

- `long vtsSetWFParams (char Target[], double timeIncrement, double pause, dword numOfRepeats); // form 1`
- `long SysVarNamespace.SetWFParams (char Target[], double timeIncrement, double pause, dword numOfRepeats, double startDelay, dword startPoint); // form 2`

## Description

The function configures the parameters for the output of a voltage or resistance curve or bitstream.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **timeIncrement**: Specifies how long the value of a specified interpolation point is to be stimulated before transitioning to the next interpolation point. Depending on the module and the wave form different ranges for `timeIncrement` are valid:
  - Voltage curves on a **VT7001** module: `timeIncrement` can be 0.000001(1 µs)…0.065 (65 ms). Note that output accuracy depends highly on environmental conditions for values between 0.000001(1 µs) and 0.00001 (10 µs). Transfer to **VT System** is performed with microsecond resolution.
  - Voltage curves on a **VT2816** or **VT2004** module: `timeIncrement` can be -0.065 (-65 ms)…0.065 (65 ms). If the value is negative, the wave form is output backwards. Note that output accuracy depends highly on environmental conditions for values between -0.00001(-10 µs) and 0.00001 (10 µs). Transfer to **VT System** is performed with nanosecond resolution.
  - Resistance curves: 0.0005 (500 µs)…0.065 (65 ms) in `R>` mode and 0.001 (1 ms)…0.065 (65 ms) in `R<` mode. Transfer to **VT System** is performed with nanosecond resolution.
  - BitStreams on a **VT2516** module: `timeIncrement` can be 0.000002 (2 µs)…0.065 (65 ms). Transfer to **VT System** is performed with microsecond resolution.
  - BitStreams on a **VT2848** module: `timeIncrement` can be -0.065 (-65 ms)…0.065 (65 ms). If the value is negative, the bitstream is output backwards. Transfer to **VT System** is performed with nanosecond resolution. Note that output accuracy depends highly on environmental conditions for values between -0.00001(-10 µs) and 0.00001 (10 µs).
- **pause**: Specifies how long the stimulation is interrupted between two repetitions of the wave form. Transfer to **VT System** is performed with nanosecond resolution. Valid values: 0.0…4294.0 (4294 s).
- **numOfRepeats**: Specifies how many times in a row the curve is to be stimulated. Valid values: 0…65535 (0 means unlimited repetition of the curve).
- **startDelay**: Specifies a delay for the start of the stimulation in seconds. This makes it possible to start multiple curves in a defined sequence. This parameter is only supported by the **VT2004**, **VT2816** and **VT2848** modules. Transfer to **VT System** is performed with nanosecond resolution. Valid values: 0.0..4.0 (4 s).
- **startPoint**: Specifies the point of the stimulated curve the stimulation should begin with. This makes it possible e.g. to start multiple curves with different phase shifts without changing the curves. This parameter is only supported by the **VT2004**, **VT2816** and **VT2848** modules. Valid values: 0..4096

## Return Values

- **0**: Successful call
- **-1**: Error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.
- **-3**: One of the specified parameters is not valid.

## Example

The following example demonstrates how to use the waveform resistance output of a **VT2004** channel to simulate a sensor. In the example a waveform called **WaveForm.TXT** is loaded and replayed on channel **Temp_Sensor**.

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
  vtsSetStimulationMode("VTS::Temp_Sensor", 3);
  vtsSetCurveType("VTS::Temp_Sensor", 2);

  // Load waveform (the contents of waveform.TXT are listed below)
  vtsLoadWFResistance("VTS::Temp_Sensor", "C:\\WaveForm.TXT");

  // Configure waveform. Parameters:
  // TimeIncrement (time to hold each sample)       = 65ms
  // Pause (pause between two waveform repetitions) = 2s
  // NumberOfRepeats (number of repetitions)        = 3
  vtsSetWFParams("VTS::Temp_Sensor", 0.065, 2.0, 3);

  // Start stimulation with the previously configured waveform
  vtsStartStimulation("VTS::Temp_Sensor");
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
    // TimeIncrement (time to hold each sample)       = 65ms
    // Pause (pause between two waveform repetitions) = 2s
    // NumberOfRepeats (number of repetitions)        = 3
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

[SetWFParams](CAPLfunctionVTSSetWFParams.md)
