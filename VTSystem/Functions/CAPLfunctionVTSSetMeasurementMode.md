[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetMeasurementMode.md)

## CAPL Functions » VT System » SetMeasurementMode

### Valid for: CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces that correspond to a channel of the VT System module VT1004/VT1104 or to channels 1-12 of the VT System module VT2816.

### Method Syntax

- `long SysVarNamespace.SetMeasurementMode (eVTSMeasurementMode Mode); // VT1004/VT1104`
- `long SysVarNamespace.SetMeasurementMode (eVTS2816MeasurementMode Mode); // VT2816`

### Description

Controls the internal measuring instrument.

- **VT1004/VT1104**: It is possible to switch between direct and filtered differential voltage measurement as well as measurement of pin a or b to reference ground (AGND).
- **VT2816**: For the measurement channels (1-12) it is possible to switch between different voltage measurement modes and the current measurement mode.

### Parameters

- **Mode**
  - Modes for VT1004/VT1104 module: Values see [eVTSMeasurementMode](../CAPLfunctionsVTSystemEnumeration.md#eVTSMeasurementMode)
  - Modes for VT2816 module: Values see [eVTS2816MeasurementMode](../CAPLfunctionsVTSystemEnumeration.md#eVTS2816MeasurementMode)

### Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified mode is not valid.
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

### Example

This example demonstrates how change the measurement mode of a VT1004 channel. By default the voltage is measured between the two input lines **A** and **B**. This example shows how to configure a measurement between input line **A** and the VT1004 module’s **AGND**.

#### CAPL

```capl
MeasurementAToAGnd ()
{
  // Change measurement mode from differential
  // to line A against ground (AGND)
  sysvar::VTS::TempSensor.SetMeasurementMode(eVTSMeasurementModeLineAToGnd);

  // Measure the voltage between line A and AGND
  write("Current voltage: %0.2fV", @sysvar::VTS::TempSensor::Cur);
}
```

#### .NET (C#)

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

#### VT System Control

Select **TempSensor**  
Set **Sidebar** | **General** | **Meas. Mode** to **A to GND**  
Check measurement value 'Cur' for the voltage between line A and AGND

[vtsSetMeasurementMode](CAPLfunctionVTSvtsSetMeasurementMode.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)