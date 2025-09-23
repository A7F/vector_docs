# ResetSignalPolarity

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT. Currently, changing the signal polarity at measurement time is only supported by SENT channels that are mapped to a VT2710 module.

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
SensorErrorCode sysvarSensorNamespace.ResetSignalPolarity();
```

## Description

Resets the signal polarity of a simulated sensor to the initially configured value.

## Parameters

—

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
enum sensorErrorCode result;

// Reset the sensor's signal polarity
result = sysvar::SENSOR::SENT::SENSORSIM::Sensor.ResetSignalPolarity();

if (result == eSensorNoError)
{
  write("Resetting the signal polarity succeeded.");
}
else
{
  write("Resetting the signal polarity failed with code: %d", result);
}
```
