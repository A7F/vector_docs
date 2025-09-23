[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetIntegrationTime.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » SetIntegrationTime

# SetIntegrationTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variables for average and RMS measurement of appropriate channels on a VT System module.

## Method Syntax Dynamic

```plaintext
long SystemVariable.SetIntegrationTime (double IntTime);
```

## Description

Mean and RMS values are calculated in a moving measurement time window. The length of the time window can be set with this function.

## Parameters

- **IntTime**: Measurement time window in seconds.  
  VT1004/VT1104: The only permissible time settings are 128 µs (= 0.000128; mean value only), 1 ms (mean value only), 10 ms, 100 ms, and 1 s.  
  VT2516/VT7001: The permissible time settings depend on the concrete measurement values and correspond to the possible settings in the VT System configuration dialog.  
  If an invalid value is specified, the call will fail.

## Return Values

- **0**: Successful call
- **-1**: Call error, i.e. system variable does not belong to a valid VT System read value or integration time is invalid.
- **-2**: The system variable on which the command was called is not valid

## Example

This example demonstrates how to change the integration time of a VT System system variable during the measurement. The integration time is set to 1s to cancel out noise in the sensor readings. It is assumed that the sensor to be read is connected to a channel called **TempSensor** of the VT1004 module.

### CAPL

```plaintext
SetIntegrationTime ()
{
   // Set integration time to 1 second
   sysvar::VTS::TempSensor::Avg.SetIntegrationTime(1.0);

   // Output sensor readings to the Write Window every second
   while(1)
   {
      write("Average sensor value: %fV", @sysvar::VTS::TempSensor::Avg);
      TestWaitForTimeOut(1000);
   }
}
```

### .NET (C#)

```csharp
public void SetIntegrationTime()
{
    // Get VTS interface and temperature sensor channel
    IVTSystem vts = VTSystem.Instance;
    IVT1004Channel tempSensor = vts.GetChannel("TempSensor") as IVT1004Channel;
    // Set integration time to 1 second
    tempSensor.Avg.IntegrationTime = 1.0;
    // Output sensor readings to the Write Window every second
    while (true)
    {
        Vector.Tools.Output.WriteLine("Average sensor value: " + tempSensor.Avg.Value.ToString() + "V");
        Vector.CANoe.Threading.Execution.Wait(1000);
    }
}
```

### [VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md)

[vtsSetIntegrationTime](CAPLfunctionVTSvtsSetIntegrationTime.md)
