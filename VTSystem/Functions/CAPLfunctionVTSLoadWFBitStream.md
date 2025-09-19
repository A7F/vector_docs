[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSLoadWFBitStream.md)

**CAPL Functions** » **VT System** » **LoadWFBitStream**

# LoadWFBitStream

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**

The method can only be called on system variable namespaces of appropriate channels of **VT System** modules. The method may not be called in any CAPL handler routines or in ECU nodes. It may only be called in the context of the MainTest method of a test module.

## Method Syntax

`long SysVarNamespace.LoadWFBitStream (char filepath[]);`

## Description

The function loads a bitstream (a sequence of bit values) for the channel from the specified file. The bitstream is used to stimulate the ECU using a digital signal.

## Parameters

- **filepath**: Path of the file containing the bitstream. The path can be given absolute or relative to the CANoe DE Family configuration.

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.
- **-3**: Error when accessing the file. This can mean, for example, that the file was not found or the file format was different than expected.
- **-4**: Transfer error – The wave form could not be transferred correctly.

## Example

The following example demonstrates how to use the bitstream voltage output of a **VT2516** channel for digital stimulation. In this example a bitstream is loaded from the file **BitStream.TXT** and played back on channel **DOut**.

### Example BitStream.TXT

```plaintext
// Sample bitstream
001100110010101100
```

### CAPL

```plaintext
BitstreamOutput ()
{
  // Choose voltage stimulation and bitstream curve type
  sysvar::VTS::DOut.SetStimulationMode(1);
  sysvar::VTS::DOut.SetCurveType(3);

  // Set high and low state voltages (12V and 0V)
  sysvar::VTS::DOut.SetPWMVoltageHigh(12.0);
  sysvar::VTS::DOut.SetPWMVoltageLow(0.0);

  // Load bitstream (the contents of BitStream.TXT are listed below)
  sysvar::VTS::DOut.LoadWFBitStream("C:\\BitStream.TXT");

  // Configure bitstream. Parameters:
  // TimeIncrement (time to hold each sample)      = 10µs
  // Pause (pause between two waveform repetitions) = 5ms
  // NumberOfRepeats (number of repetitions)       = 0 (unlimited)
  sysvar::VTS::DOut.SetWFParams(0.0001, 0.005, 0);

  // Output the configured bitstream for 10 seconds
  sysvar::VTS::DOut.StartStimulation();
  TestWaitForTimeout(10000);
  sysvar::VTS::DOut.StopStimulation();
}
```

### .NET (C#)

```csharp
public void BitstreamOutput()
{
    // Get VTS interface and VT2516 channel
    IVTSystem vts = VTSystem.Instance;
    IVT2516Channel digiOut = vts.GetChannel("DOut") as IVT2516Channel;

    // Choose voltage stimulation and bitstream curve type
    digiOut.SetStimulationMode(StimulationMode.Voltage, CurveType.BitStream);

    // Set high and low state voltages (12V and 0V)
    digiOut.PWMVoltageHigh.Value = 12.0f;
    digiOut.PWMVoltageLow.Value = 0.0f;

    // Load bitstream (the contents of BitStream.TXT are listed below)
    digiOut.LoadWFBitStream("C:\\BitStream.TXT");
    // Configure bitstream. Parameters:
    // TimeIncrement (time to hold each sample)      = 10µs
    // Pause (pause between two waveform repetitions) = 5ms
    // NumberOfRepeats (number of repetitions)       = 0 (unlimited)
    digiOut.SetWFParams(0.0001, 0.005, 0);

    // Output the configured bitstream for 10 seconds
    digiOut.StartStimulation();
    Vector.CANoe.Threading.Execution.Wait(10000);
    digiOut.StopStimulation();
}
```

### VT System Control

Select **DOut**

Set **Sidebar** | **Output Settings** | **Stim Mode** to **Active**  
Set **Sidebar** | **Output Settings** | **Curve Type** to **Bitstream**  
Set **Sidebar** | **Output Settings** | **Voltage High** to **5.0**  
Set **Sidebar** | **Output Settings** | **Voltage Low** to **0.0**  
Set **Sidebar** | **Bitstream Output** | **Bitstream** to **BitStream.txt**  
Set **Sidebar** | **Bitstream Output** | **Parameters | Time Increment** to **0.0001**  
Set **Sidebar** | **Bitstream Output** | **Parameters | Pause** to **0.005**  
Set **Sidebar** | **Bitstream Output** | **Parameters | Repeats** to **0**  
Click **Sidebar** | **Output Settings** | **Start Stimulation**  
Wait for 10 seconds  
Click **Sidebar** | **Output Settings** | **Stop Stimulation**

[vtsLoadWFBitStream](CAPLfunctionVTSvtsLoadWFBitStream.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
