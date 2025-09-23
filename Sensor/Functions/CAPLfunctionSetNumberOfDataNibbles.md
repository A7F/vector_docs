# SetNumberOfDataNibbles

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT. Currently, changing the number of data nibbles at measurement time is only supported by SENT channels that are mapped to a VT2710 module.

## Method Syntax

`SensorErrorCode sysvarSensorNamespace.SetNumberOfDataNibbles(dword numDataNibbles);`

## Description

Sets the number of data nibbles of a simulated sensor to the given value.

## Parameters

- **numDataNibbles**  
  The number of data nibbles.  
  Valid range: 1-6 nibbles

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
enum sensorErrorCode result;

// Change the sensor's number of data nibbles to 4
result = sysvar::SENSOR::SENT::SENSORSIM::Sensor.SetNumberOfDataNibbles(4);

if (result == eSensorNoError)
{
  write("Changing sensor data nibbles succeeded.");
}
else
{
  write("Changing sensor data nibbles failed with code: %d", result);
}
```
