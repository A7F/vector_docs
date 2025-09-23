# ResetNumberOfDataNibbles

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT. Currently, changing the number of data nibbles at measurement time is only supported by SENT channels that are mapped to a VT2710 module.

## Method Syntax

SensorErrorCode sysvarSensorNamespace.ResetNumberOfDataNibbles();

## Description

Resets the number of data nibbles of a simulated sensor to the initially configured value.

## Parameters

—

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;

// Reset the sensor's number of data nibbles
result = sysvar::SENSOR::SENT::SENSORSIM::Sensor.ResetNumberOfDataNibbles();

if (result == eSensorNoError)
{
  write("Resetting sensor data nibbles succeeded.");
}
else
{
  write("Resetting sensor data nibbles failed with code: %d", result);
}
```
