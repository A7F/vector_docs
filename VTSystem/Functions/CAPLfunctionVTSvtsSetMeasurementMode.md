[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSetMeasurementMode.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » vtsSetMeasurementMode

# vtsSetMeasurementMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long vtsSetMeasurementMode (char Target[], eVTSMeasurementMode Mode); // VT1004/VT1104
long vtsSetMeasurementMode (char Target[], eVTS2816MeasurementMode Mode); // VT2816
```

## Description

Controls the internal measuring instrument.

- **VT1004/VT1104**: It is possible to switch between direct and filtered differential voltage measurement as well as measurement of pin a or b to reference ground (AGND).
- **VT2816**: For the measurement channels (1-12) it is possible to switch between different voltage measurement modes and the current measurement mode.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **Mode**:
  - Modes for **VT1004/VT1104** module: Values see [eVTSMeasurementMode](../CAPLfunctionsVTSystemEnumeration.md#eVTSMeasurementMode)
  - Modes for **VT2816** module: Values see [eVTS2816MeasurementMode](../CAPLfunctionsVTSystemEnumeration.md#eVTS2816MeasurementMode)

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified mode is not valid.
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

This example demonstrates how to change the measurement mode of a **VT1004** channel. By default, the voltage is measured between the two input lines **A** and **B**. This example shows how to configure a measurement between input line **A** and the **VT1004** module’s **AGND**.

### CAPL

```capl
{
  // Change measurement mode from differential
  // to line A against ground (AGND)
  vtsSetMeasurementMode("VTS::TempSensor", eVTSMeasurementModeLineAToGnd);

  // Measure the voltage between line A and AGND
  write("Current voltage: %0.2fV", @sysvar::VTS::TempSensor::Cur);
}
```

### .NET (C#)

```csharp
public void MeasurementAToAGnd()
{
    // Get VTS interface and VT1004 channel
    IVTSystem vts = VTSystem.Instance;
    IVT1004Channel tempSensor = vts.GetChannel("TempSensor") as IVT1004Channel;

    // Change measurement mode from differential
    // to line A against ground (AGND)
    tempSensor.MeasurementMode.Value = MeasurementMode.LineAToGnd;

    // Print measurement results to Write Window
    Vector.Tools.Output.WriteLine("Current voltage: " + tempSensor.Cur.Value + "V");
}
```

### [VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md)

Select **TempSensor**  
Set **Sidebar** | **General** | **Meas. Mode** to **A to GND**  
Check measurement value 'Cur' for the voltage between line A and AGND

[SetMeasurementMode](CAPLfunctionVTSSetMeasurementMode.md)
