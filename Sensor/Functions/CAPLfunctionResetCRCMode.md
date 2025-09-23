# ResetCRCMode

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT.

## Method Syntax

`SensorErrorCode sysvarSensorNamespace.ResetCRCMode();`

## Description

Resets the CRC mode of a sensor to the initially configured value.

If short serial messages are selected, this method also resets the CRC algorithm used to calculate the serial message checksum.

## Parameters

—

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;

// Reset the sensor's pause mode
result = sysvar::SENSOR::SENT::SENSORSIM::Sensor.ResetCRCMode();

if (result == eSensorNoError)
{
    write("Resetting sensor CRC mode succeeded.");
}
else
{
    write("Resetting sensor CRC mode failed with code: %d", result);
}
```
