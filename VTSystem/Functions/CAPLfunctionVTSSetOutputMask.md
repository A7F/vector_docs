[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetOutputMask.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » SetOutputMask

# SetOutputMask

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces of appropriate channels of VT System modules.

## Method Syntax

`long SysVarNamespace.SetOutputMask (dword RowMask);`

## Description

Activates the requested rows of a switch matrix module for dynamic stimulation (PWM, Bitstreams). The row selection is binary encoded into the call parameter.

## Parameters

- **RowMask**: Binary interpreted 32bit unsigned integer value where the least significant five bits encode the connection of the corresponding matrix row with the current matrix channel.

  The assignment of matrix rows to bits of **RowMask** is implemented as follows:
  - Matrix Row 1 is activated with Bit0
  - Matrix Row 2 is activated with Bit1
  - Matrix Row 3 is activated with Bit2
  - Matrix Row 4 is activated with Bit3
  - Direct Switch is activated with Bit 4 (channel 5-8)

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.

## Example

The following example demonstrates how an identical switch sequence defined in **MyBitstream.txt** (e.g. a bouncing contact simulation) is applied subsequently to all rows of a VT2832 channel.

### CAPL

```plaintext
  int iRow;

  // This calls the method SetCurveType on VTS::MyMatrixChannel
  sysvar::VTS::MyMatrixChannel_1.SetCurveType(eVTSCurveTypeBitStream);

  // This calls the method LoadWFBitStream on VTS::MyMatrixChannel_2
  sysvar::VTS::MyMatrixChannel_1.LoadWFBitStream("MyBitstream.txt");

  // Configure waveform Parameters:
  // TimeIncrement (time to hold each sample)       = 20ms
  // Pause (pause between two waveform repetitions) = 0s
  // NumberOfRepeats (number of repetitions)        = 1

  sysvar::VTS::MyMatrixChannel_1.SetWFParams(0.020, 0.0, 1);

  // Start stimulation
  sysvar::VTS::MyMatrixChannel_1.StartStimulation();

  for (iRow = 1; iRow < 16; iRow = iRow << 1)
  {
    // This calls the method SetOutputMask on VTS::MyMatrixChannel
    sysvar::VTS::MyMatrixChannel_1.SetOutputMask(iRow);
  }

  // Stop Stimulation
  sysvar::VTS::MyMatrixChannel_1.StopStimulation();
```

### .NET (C#)

—

### [VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md)

Select **MyMatrixChannel_1**  
Set **Sidebar** | **Output Settings** | **Curve Type** to **Bitstream**  
Set **Sidebar** | **Bitstream Output** | **Bitstream** to **MyBitstream.txt**  
Set **Sidebar** | **Bitstream Output** | **Parameters | Time Increment** to **0.02**  
Set **Sidebar** | **Bitstream Output** | **Parameters | Pause** to **0.0**  
Set **Sidebar** | **Bitstream Output** | **Parameters | Repeats** to **0**  
Click **Sidebar** | **Output Settings** | **Start Stimulation**  
Enable each row, one by one  
Set **Sidebar** | **PWM /Bitstream Output Mask** | **Row 1** to **ON**  
Set **Sidebar** | **PWM /Bitstream Output Mask** | **Row 1** to **OFF**  
Set **Sidebar** | **PWM /Bitstream Output Mask** | **Row 2** to **ON**  
Set **Sidebar** | **PWM /Bitstream Output Mask** | **Row 2** to **OFF**  
Set **Sidebar** | **PWM /Bitstream Output Mask** | **Row 3** to **ON**  
Set **Sidebar** | **PWM /Bitstream Output Mask** | **Row 3** to **OFF**  
Set **Sidebar** | **PWM /Bitstream Output Mask** | **Row 4** to **ON**  
Set **Sidebar** | **PWM /Bitstream Output Mask** | **Row 4** to **OFF**  
Click **Sidebar** | **Output Settings** | **Stop Stimulation**

[vtsSetOutputMask](CAPLfunctionVTSvtsSetOutputMask.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
