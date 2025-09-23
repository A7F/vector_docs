# SetCrcMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT.

## Method Syntax

SensorErrorCode sysvarSensorNamespace.SetCRCMode(dword crcMode);

## Description

Sets the CRC mode of a sensor to the given value.

If short serial messages are selected, this method also changes the CRC algorithm used to calculate the serial message checksum.

## Parameters

- **crcMode**: The CRC mode to be set.
  - 3 ([eSentRecommendedCrc](../CAPLfunctionsSensorEnumeration.md)): Recommended CRC mode
  - 4 ([eSentLegacyCrc](../CAPLfunctionsSensorEnumeration.md)): Legacy CRC mode

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;

// Use the legacy algorithm to calculate the sensor checksum
result = sysvar::SENSOR::SENT::SENSORSIM::Sensor.SetCRCMode(eSentLegacyCrc);

if (result == eSensorNoError)
{
  write("Changing sensor CRC mode succeeded.");
}
else
{
  write("Changing sensor CRC mode failed with code: %d", result);
}
```
