# SetSerialMessagingMode

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT.

## Method Syntax

SensorErrorCode sysvarSensorNamespace.SetSerialMessagingMode(dword serialMsgMode);

## Description

Sets the serial messaging mode of a sensor to the given value.

## Parameters

- **serialMsgMode**  
  The serial messaging mode to be set.
  - 0: Short mode
  - 1: Enhanced mode

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
enum sensorErrorCode result;

// Change the sensor's serial message mode to "Enhanced"
result = sysvar::SENSOR::SENT::SENSORSIM::Sensor.SetSerialMessagingMode(1);

if (result == eSensorNoError)
{
  write("Changing sensor serial messaging mode succeeded.");
}
else
{
  write("Changing sensor serial messaging failed with code: %d", result);
}
```
