[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsResetMinMax.md)

**CAPL Functions** » **VT System** » **vtsResetMinMax**

# vtsResetMinMax

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long vtsResetMinMax (char Target[]);
```

## Description

Resets the measurement of the minimum and maximum value.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise, the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

This example demonstrates how to measure the minimum and maximum voltages at a **VT1004** channel. After the test is started, the old min and max values are reset. Then the input voltage is analyzed for 5 seconds. After that, the new min and max voltages are output to the Write Window of the CANoe DE Family / the test report.

### CAPL

```plaintext
PerformMinMaxMeasurement ()
{
  // Initialize and wait for 5 seconds
  vtsResetMinMax("VTS::TempSensor");
  TestWaitForTimeOut(5000);

  // Print measurement results to Write Window
  write("Measured voltage minimum: %0.2fV", @sysvar::VTS::TempSensor::Min);
  write("Measured voltage maximum: %0.2fV", @sysvar::VTS::TempSensor::Max);
}
```

### .NET (C#)

```csharp
public void PerformMinMaxMeasurement()
{
    // Get VTS interface and VT1004 channel
    IVTSystem vts = VTSystem.Instance;
    IVT1004Channel tempSensor = vts.GetChannel("TempSensor") as IVT1004Channel;

    // Initialize and wait for 5 seconds
    tempSensor.ResetMinMax();
    Vector.CANoe.Threading.Execution.Wait(5000);

    // Print measurement results to Write Window
    Vector.Tools.Output.WriteLine("Measured voltage minimum: " + tempSensor.Min.Value.ToString() + "V");
    Vector.Tools.Output.WriteLine("Measured voltage maximum: " + tempSensor.Max.Value.ToString() + "V");
}
```

### VT System Control

[VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md)

- Select **TempSensor**
- Click **Sidebar** | **Reset Min/Max** | Wait for 5 seconds
- Check measurement values 'Min' and 'Max'

[ResetMinMax](CAPLfunctionVTSResetMinMax.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
