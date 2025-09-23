# ResetSerialMessagingMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT.

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax  
`SensorErrorCode sysvarSensorNamespace.ResetSerialMessagingMode();`

## Description

Resets the serial messaging mode of a sensor to the initially configured value.

## Parameters

—

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;

// Reset the sensor's serial messaging mode
result = sysvar::SENSOR::SENT::SENSORSIM::Sensor.ResetSerialMessagingMode();

if (result == eSensorNoError)
{
  write("Resetting sensor serial messaging mode succeeded.");
}
else
{
  write("Resetting sensor serial messaging mode failed with code: %d", result);
}
```
