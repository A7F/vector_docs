# ResetPauseMode

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT. Currently, changing the pause mode is only supported by SENT channels that are mapped to a VT2710 module.

## Method Syntax

SensorErrorCode sysvarSensorNamespace.ResetPauseMode();

## Description

Resets the pause mode and pause length of a simulated sensor to the initially configured values.

## Parameters

—

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;

// Reset the sensor's pause mode
result = sysvar::SENSOR::SENT::SENSORSIM::Sensor.ResetPauseMode();

if (result == eSensorNoError)
{
  write("Resetting sensor pause mode succeeded.");
}
else
{
  write("Resetting sensor pause mode failed with code: %d", result);
}
```
